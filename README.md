# AAMAS-2-page-proof

\begin{theorem}\label{thm:identical-students-EF1-CC+}
    \cref{alg:identical-students-EF1-CC} outputs an EF1-CC+ allocation under identical additive non-negative utilities and uniform credit caps
    in $O\left(n \cdot m \cdot \sum_{j = 1}^m u(j)\right)$ time. 
\end{theorem}
\iffalse
\begin{proof}
    For establishing EF1-CC+~\cref{def:ef1-cc}, we need to prove (1)~by the end of the algorithm, no student envies another student by more than one course and (2)~no student envies \Charity. 

    To prove the second claim is easy: the algorithm terminates when the lowest-utility student no longer desires to swap any courses from \Charity. In other words, she does not envy the \Charity. Since all the students have identical utilities and uniform credit caps, the other students (with utilities at least that of the lowest-utility student) also do not envy the \Charity. 

    We prove the first claim: for any two students $s$ and $s'$, student $s$ never envies $s'$ by more than one course throughout the algorithm. We prove this claim for Phase $1$ and Phase $2$ separately. We first prove via contradiction that when Phase $1$ ends, our allocation satisfies
    EF1. Suppose that student $s$ envies $s'$ by more than one item.
    Then it is easy to see that the last course given to $s'$ should not have been offered to $s'$ but someone else, as $s'$ was not the lowest utility student before its last course was assigned.

    Now we prove this claim for Phase $2$ via induction.
    %\samir{How's this for a proof  for Phase 1? To see that when Phase 1 ends, our allocation satisfies EF1, we prove this by contradiction. Imagine that student $s$ strongly envies $s'$ (in other words EF1 is not true). Then it is easy to see that the last course given to $s'$ should not have been offered to $s'$ but someone else, as $s'$ was not a student with lowest utility before its last course was assigned.} 
    %\qq{Keep contradiction proof for Phase 1 and get rid of induction for Phase 1.}
    The base case: the first step of the algorithm assigns the first course to the lowest-utility student, which could be any student, since everyone starts out with an empty allocation. Thus, if $s'$ is assigned the first course, then $s$ only envies $s'$ by at most one course. For the inductive step, we order the sets of courses given to students by the algorithm; let this order be $\sigma$. For example, if courses $\{x,y,z\}$ is the $i$-th set of courses to be given simultaneously to a student, say student $s_j$, then $\sigma_i = \{x,y,z\}$; if the next round of courses to be given to a student consists of only course $q$, then $\sigma_{i+1} = \{q\}$.
    We say ``set'' because in the second phase of the algorithm (from \cref{line:identical-students-second-half} to \cref{line:end-of-identical-students-algo}), multiple courses from the \Charity can be assigned simultaneously to a student. Assuming the inductive hypothesis where $s$ does not envy $s'$ by more than one course after the set of courses $\sigma_{i}$ is assigned, we have to prove that $s$ does not envy $s'$ by more than one course after $\sigma_{i+1}$ is assigned. 
    %We prove this for the two phases of the algorithm: Phase 1 before \cref{line:identical-students-second-half} and Phase 2 including it and after. 
    
    %In Phase $1$, assume $s$ does not envy $s'$ after course $\sigma_{i}$ was assigned, then if $s'$ were to be assigned course $\sigma_{i+1}$, then $s$ can only envy $s'$ by at most one course. On the other hand, if $s$ envies $s'$ by one course after $\sigma_{i}$, then that means $s'$ has a higher utility than $s$ and thus will not be assigned course $\sigma_{i+1}$. 
    
    In Phase $2$, if $s$ envies $s'$ by one course after $\sigma_{i}$, then that means $s'$ has a higher utility than $s$, and thus $s'$ will not be assigned the set of courses $\sigma_{i+1}$, which is the same argument as above. If $s$ did not envy $s'$ after the assignment of courses in $\sigma_{i}$, however, we must make a different argument than above due to the fact that multiple courses can be assigned simultaneously to a student in the second phase of the algorithm. If $s'$ is the lowest-utility student after the assignment of $\sigma_{i}$ and gets assigned $\sigma_{i+1}$ from the \Charity, then $s$ would envy $s'$ by at most one course. The reason for this is due to the selection of the value $t$ in \cref{line:choose-t}. Since $t$ is the smallest number such that letting $s'$ make a new bundle for herself by including the first $t$ courses in the \Charity makes $s'$ strictly prefer that new bundle to her current allocation $A_{s'}$. 
    On the other hand, by~\cref{line-identical:take-mis,line-identical:continue-iteration}, a bundle including just the first $t-1$ courses from \Charity and the current allocation of $s'$ is valued at strictly lower than $A_{s'}$. This means that if $s$ were to envy the new allocation of $s'$ after the assignment of $\sigma_{i+1}$, we can remove $\charity_{t}$ from that $\sigma_{i+1}$ so that $s$ no longer envies $s'$. The claim holds for $\sigma_{l}$ where $l$ is the index of the last set of courses assigned, and any two students are symmetrical. This completes the proof.
\end{proof}
