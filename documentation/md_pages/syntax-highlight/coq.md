# COQ

usage: **\`\`\`coq**

renders:

```coq
Require Import Coq.Lists.List.

Section with_T.
  Context {T : Type}.

  Fixpoint length (ls : list T) : nat :=
    match ls with
    | nil => 0
    | _ :: ls => S (length ls)
    end.
End with_T.

Definition a_string := "hello\" world".
