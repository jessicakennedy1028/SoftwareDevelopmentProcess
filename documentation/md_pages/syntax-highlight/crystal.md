# Crystal

usage: **\`\`\`crystal**

renders:

```crystal
lib LibC
  WNOHANG = 0x00000001

  @[ReturnsTwice]
  fun fork : PidT
  fun getpgid(pid : PidT) : PidT
  fun kill(pid : PidT, signal : Int) : Int
  fun getpid : PidT
  fun getppid : PidT
  fun exit(status : Int) : NoReturn

  ifdef x86_64
    alias ClockT = UInt64
  else
    alias ClockT = UInt32
  end

  SC_CLK_TCK = 3

  struct Tms
    utime : ClockT
    stime : ClockT
    cutime : ClockT
    cstime : ClockT
  end

  fun times(buffer : Tms*) : ClockT
  fun sysconf(name : Int) : Long
end

class Process
  def self.exit(status = 0)
    LibC.exit(status)
  end

  def self.pid
    LibC.getpid
  end

  def self.getpgid(pid : Int32)
    ret = LibC.getpgid(pid)
    raise Errno.new(ret) if ret < 0
    ret
  end
end
