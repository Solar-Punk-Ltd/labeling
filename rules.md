# Rules for LLMs

DO NOT comment on issues when adding labels, even if the label not exists yet in the repository.
USE the github MCP tools.

# Rules for Issues and Pull Requests
| Label | Description |
| ----- | ----------- |
| dif:easy | Someone with a little familiarity can pick up |
| dif:expert | Extensive knowledge (implications, ramifications) required |
| dif:hard | Having worked on the specific codebase is important |
| dif:medium | Prior experience is likely helpful |
| dif:trivial | Can be confidently tackled by newcomers |
| kind:architecture | Core architecture of project |
| kind:bug | A bug in existing code (including security flaws) |
| kind:discussion | Topical discussion; usually not changes to codebase |
| kind:enhancement | A net-new feature or an improvement to an existing feature |
| kind:maintenance | Work required to avoid breaking changes or harm to project's status quo |
| kind:question | A question or request for support |
| kind:refactor | Refactoring issue |
| kind:test | Testing work |
| need:analysis | Needs further analysis before proceeding |
| need:author-input | Needs input from the original author |
| need:community-input | Needs input from the wider community |
| need:documentation | The issue should not be closed before it is documented. |
| need:maintainers-input | Needs input from the current maintainer(s) |
| need:triage | Needs initial labeling and prioritization |
| P0 | Critical: Tackled by core team ASAP |
| P1 | High: Likely tackled by core team if no one steps up |
| P2 | Medium: Good to have, but can wait until someone steps up |
| P3 | Low: Not priority right now |
| P4 | Very low priority |
| status:backlog | Conscious decision to pause or backlog |
| status:blocked | Unable to be worked further until needs are met (see 'need:*' category) |
| status:duplicate | This issue or pull request already exists |
| status:in-progress | In progress |
| status:inactive | No significant work in the previous month |
| status:ready | Ready to be worked |

# Labels

All issues should ble lableled with kind, dfficulty and priority lables.

## `gh label list` output
```
NAME                    DESCRIPTION                                                              COLOR  
good first issue        Good for newcomers                                                       #A16610
help wanted             Seeking public contribution on this                                      #008672
invalid                 This doesn't seem right                                                  #e4e669
kind:bug                A bug in existing code (including security flaws)                        #fc2929
kind:enhancement        A net-new feature or an improvement to an existing feature               #c7def8
kind:question           A question or request for support                                        #c7def8
needs documentation     The issue should not be closed before it is documented.                  #4F92BD
status:duplicate        This issue or pull request already exists                                #E7FAC5
wontfix                 This will not be worked on                                               #ffffff
type:pull-request                                                                                #ededed
type:issue                                                                                       #ededed
(ノಠ益ಠ)ノ彡┻━┻         ...                                                                      #d93f0b
dependencies            Pull requests that update a dependency file                              #0366d6
dif:easy                Someone with a little familiarity can pick up                            #FFE375
dif:expert              Extensive knowledge (implications, ramifications) required               #D9AD00
dif:hard                Having worked on the specific codebase is important                      #F8C600
dif:medium              Prior experience is likely helpful                                       #FFD737
dif:trivial             Can be confidently tackled by newcomers                                  #FFF0B5
env:browser             Relates to browser environment                                           #c5def5
env:nodejs              Relates to NodeJS environment                                            #c5def5
kind:architecture       Core architecture of project                                             #c7def8
kind:discussion         Topical discussion; usually not changes to codebase                      #c7def8
kind:maintenance        Work required to avoid breaking changes or harm to project's status quo  #c7def8
kind:refactor           Refactoring issue                                                        #c7def8
kind:test               Testing work                                                             #c7def8
need:analysis           Needs further analysis before proceeding                                 #ededed
need:author-input       Needs input from the original author                                     #ededed
need:community-input    Needs input from the wider community                                     #ededed
need:maintainers-input  Needs input from the current maintainer(s)                               #ededed
need:triage             Needs initial labeling and prioritization                                #ededed
P0                      Critical: Tackled by core team ASAP                                      #b60205
P1                      High: Likely tackled by core team if no one steps up                     #d93f0b
P2                      Medium: Good to have, but can wait until someone steps up                #e99695
P3                      Low: Not priority right now                                              #f9d0c4
P4                      Very low priority                                                        #f9d0c4
status:backlog          Conscious decision to pause or backlog                                   #BCF059
status:blocked          Unable to be worked further until needs are met (see 'need:*' category)  #E77E7F
status:in-progress      In progress                                                              #BCF059
status:inactive         No significant work in the previous month                                #E7FAC5
status:ready            Ready to be worked                                                       #BCF059
pull-request                                                                                     #ededed
autorelease: pending                                                                             #ededed
autorelease: tagged                                                                              #ededed
Epic                                                                                             #4660F9
env:electron            Relates to Electron environment                                          #c5def5
desktop                                                                                          #FEF352
```