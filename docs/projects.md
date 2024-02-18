<a name=top><br>
  <p align=center>&nbsp;<a href="/README.md#top">home</a> ::
  <a href="/docs/syllabus.md#top">syllabus</a> ::
  <a href="https://docs.google.com/spreadsheets/d/16yxmklx4zvmfAHE7QocOQZZ4v4UxD5ktJHWMJEjBcMI/edit#gid=0">groups</a> ::
  <a href="/LICENSE.md#top">&copy;&nbsp;2024</a>, <a href="http:/timm.fyi">Tim Menzies</a><br>
  <a href="/README.md#top"><img width=600  
     src="/etc/img/ase24.png"></a></p>

# projects

flash. 30 is enough with tabu. what about just do 30 rand with tabu?
- had to do tabu for lasrge spaces maybe prune anything . 
  - incrementally prune rows
    - crete a row object with a flag "alive"
      - delete anything that is closwer than 20,40,60,80% sum distance to max? (so 4 runs)
    - dont do distance to all

```
budget0 = 4  (say)
buddget = 30 (say)
alpha=2 # but might have values -3 to +3
done,todo = rows[:budget0],rows[budget0:]
ds=NUM()
max=0
for i in range(budget0+1, budget-budget0):
  tmp = todo
  todo = []
  for now in tmp:
    d=sum(dist(now,b4) for b4 in done)
    ds.add(d)
    if d > max: max,best=d,now
    if d > d.mu + alpha *d.sd: todo += [row] # only keep distant things in todo
  done += [best]
  done = sorted(done, key=self.d2h)
  print(i, done[0]) 
```

rules with disjunctions. just conjucts? other tricks for redcing the ranges to slots?

replace NB with FFT.  use B0=6, see if youc an get  model and optimization is  one go. Note: yu will have to implemt ft trees. not hard.
but rememember the $2^D$ trick 

so many asusmptions in the maths. what
happens if they are vioalated? can you
build an isntane generator that cretes
problems that are easily solved/ hard to solve
via the methods of this class?

## basic

banchmark smo againt random, rrp

for https://arxiv.org/pdf/2311.17483.pdf, fig 9, what support can you add to support (say) 5 of the lefthand side reqirements? comparing mylo and gate, which is better than the other

table7 of https://arxiv.org/pdf/2311.17483.pdf: how many of these have goals we can optimize for?

table9 of https://arxiv.org/pdf/2311.17483.pdf: how well do any of those work with < 30 samples? can you think of some hybrid of gate/mylo that mught augment/replace any of these?

## process

- prior knowledge
   - LLMs
   - assume that we've already run a choice session before
     - so divide training data in half
     - do what we nornally do on one half
       - see how quickly we can do it again 
- multiple xperts
  - dont ask one oracle, ask n
  - warning: experts often disagree. how to handle disputes between experts
    - some rig where the level of disagreement is a dial and can crank "disagree" up from 0 to always (with many stops in between)
- management team: milestones management, user liason,
  task priorization
- tooling team: doc, scripts, short cuts, pre-, post- commit hooks
  - please consider pdoc or pycco
- testing team: lots of tests, maintaining the test suite,
  running the test suite, test case prioriization
- coding team; new functionality
  - divide the code base into N bits
- the optimization team. welcome to software 2.0
  - Software 2.0 most often the source code comprises 
   -  the dataset that defines the desirable behavior 
   - the architecture that gives the rough skeleton of the code, 
     but with many details (the config options) to be filled in. 
   - some optimizaion strategy that keeps reviewing the
     data to adjust the config options.

lcocal vs gloab, reset at each stage

check if (b+r)/(b-r) does better

## Tasks
- apply rrp to some new domain (in se)
- x is y and when i code it that way, i get results (for x or y) that
  beat the prior state of the art (simpler and faster or better)
- destroy all this tech. find someway to improta tables
  of data with no goal info and after minimal questions
  learn which rows a preferred by most users
  - note: I don't know how to do this. 
- sway vs sequential model optimize (bayes)
- try different clustering. different recursive bi-cluster
- try a project managers toolkit. 
- try and improve xiao's stuff
- anyway to map subjective opinions (from chatgpt) into search-based?
  - https://arxiv.org/pdf/2311.11081.pdf
  - anyway to bias (in a good way), sway's search using LLMs?   
    - maybe not https://arxiv.org/pdf/2306.13298.pdf (\*)
  - hint: maybe dont use chatgpt but a local LLMso
    - see  "LLMs on the command line" at https://www.infoworld.com/article/3705035/5-easy-ways-to-run-an-llm-locally.html
    - see also https://www.infoworld.com/article/3700869/14-llms-that-arent-chatgpt.html
- testing our tools via chatgpt https://dl.acm.org/doi/pdf/10.1145/3624032.3624035
  - make sure you have a baseline (testing via some other defendable approach)

(\*) but see vivek's paper suggesting that don't matter.

- comapre rrp vs cloassification or regresison algorithms for SE taksks
- Table 1,2 of [this paper](https://csdl-downloads.ieeecomputer.org/trans/ts/5555/01/10314766.pdf?Expires=1703969010&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9jc2RsLWRvd25sb2Fkcy5pZWVlY29tcHV0ZXIub3JnL3RyYW5zL3RzLzU1NTUvMDEvMTAzMTQ3NjYucGRmIiwiQ29uZGl0aW9uIjp7IkRhdGVMZXNzVGhhbiI6eyJBV1M6RXBvY2hUaW1lIjoxNzAzOTY5MDEwfX19XX0_&Signature=vkbhgVvW8l9aPJz9K14TAH178rlS9sBiht6nrLq8X~BcgvnTax~LL6GRoIhRLUVMkmWVgyMW-eSqfi3Pe1WlHb5oMxmQxSSIyz4gN5tjAr3MYergqd4OPSfTxjEm2hN-pBXwVpaeMHZTJ077YMVcTIqMqn9bJmzaOHvhDKYeJa3K~ZmFQuvUzDL4263mT8NQr-nPTi6136O1DmqtxIOKXVpMSddcPhNx~2GWrEX63O7mEkSfS6vBfZpsYXMHqeEkqsoxd3H5SziuAcoHt0kr7ttdYGSUrmjicDXEOd19gXC8ksZmgx2Mw2dBLI-LBEvTsCfgwF0d8ueYR1F3AiFeFw__&Key-Pair-Id=K12PMWTCQBDMDT)
  discussed ways to reduce human fatigure. any work at our scale? (les than 30 questions)
  - R. Casamayor, C. Cetina, O. Pastor and F. Perez, "Studying the Influence and Distribution of the Human Effort in a Hybrid Fitness Function for Search-Based Model-Driven Engineering" in IEEE Transactions on Software Engineering, vol. 49, no. 12, pp. 5189-5202, 2023.
doi: 10.1109/TSE.2023.3329730
- another approach is to do fix the daa drougth via data synthesis
  - take all that is known of the independent attributes
  - generate a very large sample of those attributes. attach known labels. label everything 
    else via (e.g.) expected value k=2 nearest neighbors.
    - then do (say) classification on the result
    - or do optimizaiton and when new isntaces are proposed, apply k=2 nNN.

