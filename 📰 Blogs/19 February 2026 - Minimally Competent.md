```diff
+ The cards we can play.
  
Vis Tacitus
- 19 February 2026
```

#blogs #confoederatio #Y2026
![[lab_space_knn_binning.png]]<div align = "center">Lab-space kNN binning for polygon extraction and vectorisation from complex raster maps.</div>

We are not normal humans. Neither are we experts. As an indie data science studio, we have only have two core members and we must take stock of the cards we can play, almost like some sort of grotesque boardgame. These must be divided into capabilities (the pertinent skills we have and what we can reasonably accomplish), infrastructure (independent platforms that have already been built we can lean upon), weaknesses (what we find impossible to do), and end objectives (the ends to our means).

Ideally, our strategy should be asymmetric. We have nearly no good path towards fixing our weaknesses and so we should seek to maximally leverage the capabilities and infrastructure we do have to achieve our objectives whilst avoiding them as much as possible.

## The Objectives of the Minimally Competent

**Low-hanging fruit.** These are line items critical to the modern information and attention economy that others have neglected; not because they are hard, or because we are the most talented in the room, but because they see it as beneath them. 

These tasks include database construction, cleaning, synthesis, leveraging paywalled sources by industrially bypassing, caching, and mirroring them, and their free analysis and publication by inhabiting digital greyzones to their fullest extent. Rationally, Confoederatio's end-state should be a parallel digital society in which we hold maximally autarkic control of the entire tech stack for information production, regardless of whether others are along for the ride.

**What does information production mean?**

Its tangible endpoint is a complete digital twin of Earth with total spatiotemporal awareness. Its production would involve both a Livemap for ingesting live data sources and their real-time scraping, cleaning, and analysis (focused on ORBATs, logistics, geopol, and finance), as well as Histmap (historical map) for historical economics, demography, and politics.

If we live in an information economy, an information-complete picture is the only logical endpoint. Our primary advantage in racing to build this crystal ball, hazy as it may be, is that no one else has realised it is the endgoal yet. And because no one on the internet can be convinced, no one will.

We, the minimally competent, have to be the open-source vanguard. Better us than some corpo.
## Infrastructure

![[naissance_1.7b_chukchi.png]]

<div align = "center">Naissance 1.7b Chukchi showing its ability for spatiotemporal keyframing and DAG construction in-GUI.</div>

To this end, we have already built significant infrastructure and test capabilities which have proven mature and production-ready. These include both past databases manufactured under our Research Division (CRD) as well as software and data pipeline engines built by CTD. 

Software engines specifically exist to automate the encoding of data by allowing the flexible construction of data pipelines via node editors and multi-agent orchestration, as all software is merely a form of continually manipulating and projecting data. 

Additionally, beta tooling suites whose security has not been proven have also been developed merely to prove capabilities given certain tasks. These proof-of-concepts must be expanded upon and integrated into reusable software, and here these infrastructure capabilities have been asterisked.

**Software.**
- [[Vercengen]]. Software engine.
	- [[Vercengen Blacktraffic]]. Multi-agent orchestration suite with agentic toolcall, Selenium/Puppeteer, DOM extraction and data cleaning capabilities.
- [[Naissance HGIS]]. 4D geospatial data editor with both histmap/livemap capabilities.
	- Mesh warp capabilities for arbitrary projections.\*
- [[Endesnaht]]\*. Remote-control app using Cloudflare tunnels that can be remotely ported between social media platforms as well as VLAN protocols.

**Histmap.**

The historical databases we have are best-in-class, since they represent syntheses of existing calculations and have been thoroughly tested and validated.

- [[Stadestér]]. Digital urban database (3000BC-2025AD)
- [[Velkscala]]. Digital population database (10000BC-2025AD)
- [[Eoscala]]. Digital economic database (10000BC-2025AD)
- [[Atlas]]. Digital political database (3000BC-2025AD)

**Livemap.**
Only proof-of-concepts have currently been run and tested in this category.

- Automated news aggregators and geolocation. We have done this in the past via [[OMNI]].
- Chrome/Firefox spoofing that creates automated web traffic indistinguishable from regular users, with the ability to use extensions, interact with website login forms, etc.
- Heuristic AI prompting infrastructure that bypasses APIs via juggling free accounts across client-facing websites.\*
- Lab-space kNN Binning and Polygon Extraction from raster images\*. As far as we know, we have the most efficient and heuristically optimal algorithms for vectorisation outside ML approaches.
## Capabilities

Our current manpower pool is flexibly skilled: jacks in all trades, but aces of none. However, despite being time-rich, it is highly limited and stagnant, being unlikely to expand. This creates an incentive to 1) continually do less with more, and 2) race to expand capabilities and iterate quickly before the clock runs out.

Fortunately, the tooling and infrastructure we have developed is positioned to do just that. 

- Digital capabilities: anything achievable with consumer hardware (with the exception of music), we can create within a healthy time budget. Questions then shift from whether something is possible to what to prioritise.
- Physical archives: we possess physical archives as well as leaked atlases and documents for use in historical research. In particular, we have access to West German academic works which have not been digitised or made freely available.
- Proxy modelling: since we have historically worked on interpolating data over the long run and in the deep past; we have become very good at iteratively improving assessments of missing data. This is a skillset that will need continual refinement in livemap tasks.
## Weaknesses

- Digital capability gap: 3D graphics and animation\*
- Digital capability gap: music
- External AI Vendor Reliance: bad only if hyperscalers establish monopoly. If the AI bubble bursts, it is likely that compute will become cheap to rent; conversely, it is also possible that accessible open-source models and hardware may catch up, though they will be significantly degraded.
- External Vendor Reliance: scrapers must constantly be repaired until we can figure out self-healing DOM targeting and scripting and how consistently changing code can be reliably integrated into workflows and codebases.
- Formalised Maths: whilst applied knowledge might be very good by way of what we can achieve, the actual formalisation of approaches and their publication is something we are genuinely bad at.
- Limited SaaS Budgeting and Hardware: no commercial providers are available, and API accesses are out of the question. We must rely on scrapers and home-built alternatives instead. Our consumer rigs are powerful workstations, but not supercomputers. 
- Polish and Security: we never seem to be able to finish the missing 20% needed for actual mass distribution. In addition, our strained manpower means that we are unable to robustly test and ensure that our systems are secure, and the fact they have been until now is likely security by obscurity.
- Socialisation and Marketing: simply a no-go. No one is interested in what we have to say. Our strategy must then be to show, not tell, and in select forums, once core capabilities have been automated.
## Action Plans

Knowing what we know now, what can we do? The most important thing is to retain flexibility without sacrificing the integrity of our tech stack in this current fast-moving information environment. We must continue down the path of the mythical manmonth. Vendor lockouts, infosphere pollution, and increasing passivity is rendering the internet uninhabitable, likely by late 2027-2028.

**What does this mean in practice?**

1. We must get a Livemap up as soon as possible, regardless of elegance. The sooner we can start recording and artefacting data, the less catch-up we have to do in the future. It will additionally attract public interest.
2. SVEA (Stadestér, Velkscala, Eoscala, Atlas) must be ported to [[Naissance HGIS]] as soon as possible underneath a reproducible architecture.
3. All databases within SVEA must be made to be robust and to improve on their database accuracy. Current accuracy stands around 70-80% according to validation reports; whilst far above the rates seen in peer databases (i.e. HYDE, Reba et al., Maddison), it must exceed 95% to be considered research-grade. 
   Actionable plans have already been drafted at this stage, all that remains is their execution.
4. Data visualisation, animation, and publication. This must be pursued concurrently with livemap iteration and improvement. Investments in the attention economy have to be made to attract and onboard new Confoederatio members.
   
   This may raise our public profile and attention. It is likely that this will lead to frantic beta patching and a rush to catch and patch unintended exploits in our codebases as soon as possible. Because OSINT work and research relies on operating in greyzones by default, it may also attract legal attention, of which we must be careful, and as such we have to maintain a minimal attack surface - ideally, this would include efforts to preserve anonymity.