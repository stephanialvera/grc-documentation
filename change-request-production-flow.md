``` mermaid
graph TD;
    Start((Product Request)) --> CR[Change Request];
    CR --> ReviewEM[Review EM];
    ReviewEM --> |Not Approved| NoteReviewEM[Reason Note];
    NoteReviewEM --> CR;
    ReviewEM --> |Approved| MS[Migration Sheet];
    MS --> Development[Development];
    Development --> UATStg[Testing Staging];
    UATStg --> |Bug/Finding?| fixing[Fixing];
    fixing --> Development;
    UATStg--> |OK?| Deployment[Deploy Production];
    Deployment --> |Error| RP[Rollback Plan];
    RP --> fixing;
    fixing --> Deployment;
    Deployment --> |Ok?| UATProd[UAT Production];
    UATProd --> BATest[BA Testing];
    BATest --> BAGoLive[BAST Realease];
    BAGoLive --> Release;
    Release --> GoLive[Go Live];
```
