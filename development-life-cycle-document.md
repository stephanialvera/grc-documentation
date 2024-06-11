``` mermaid
graph TD;
    Start((Start)) --> BRD[Bussiness Requirement Documents];
    BRD --> PRD[Product Requirement Documents];
    PRD --> ReviewEM[Review EM];
    ReviewEM --> |Not Approved| NoteReviewEM[Reason Note];
    NoteReviewEM --> PRD[Product Requirement Documents];
    ReviewEM --> |Approved| TSD[Technical Specification Documents];
    TSD --> FSD[Functional Specification Documents];
    FSD --> Development[Development];
    Development --> UATStg[Testing Staging];
    UATStg --> |Bug/Finding?| fixing[Fixing];
    fixing --> Development;
    UATStg--> |OK?| Deployment[Deploy Production];
    Deployment --> |Error| Deployment;
    Deployment --> |Ok?| UATProd[UAT Production];
    UATProd --> BATest[BA Testing];
    BATest --> BAGoLive[BAST Realease];
    BAGoLive --> Release;
    Release --> GoLive[Go Live];
```
