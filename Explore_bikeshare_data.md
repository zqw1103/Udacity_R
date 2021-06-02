
### Explore Bike Share Data

For this project, your goal is to ask and answer three questions about the available bikeshare data from Washington, Chicago, and New York.  This notebook can be submitted directly through the workspace when you are confident in your results.

You will be graded against the project [Rubric](https://review.udacity.com/#!/rubrics/2508/view) by a mentor after you have submitted.  To get you started, you can use the template below, but feel free to be creative in your solutions!


```R
ny = read.csv('new_york_city.csv')
wash = read.csv('washington.csv')
chi = read.csv('chicago.csv')
```


```R
head(ny)
```


<table>
<thead><tr><th scope=col>X</th><th scope=col>Start.Time</th><th scope=col>End.Time</th><th scope=col>Trip.Duration</th><th scope=col>Start.Station</th><th scope=col>End.Station</th><th scope=col>User.Type</th><th scope=col>Gender</th><th scope=col>Birth.Year</th></tr></thead>
<tbody>
	<tr><td>5688089                                       </td><td>2017-06-11 14:55:05                           </td><td>2017-06-11 15:08:21                           </td><td> 795                                          </td><td>Suffolk St &amp; Stanton St                   </td><td>W Broadway &amp; Spring St                    </td><td>Subscriber                                    </td><td><span style=white-space:pre-wrap>Male  </span></td><td>1998                                          </td></tr>
	<tr><td>4096714                                                           </td><td>2017-05-11 15:30:11                                               </td><td>2017-05-11 15:41:43                                               </td><td> 692                                                              </td><td>Lexington Ave &amp; E 63 St                                       </td><td><span style=white-space:pre-wrap>1 Ave &amp; E 78 St       </span></td><td>Subscriber                                                        </td><td><span style=white-space:pre-wrap>Male  </span>                    </td><td>1981                                                              </td></tr>
	<tr><td>2173887                                                            </td><td>2017-03-29 13:26:26                                                </td><td>2017-03-29 13:48:31                                                </td><td>1325                                                               </td><td><span style=white-space:pre-wrap>1 Pl &amp; Clinton St      </span></td><td><span style=white-space:pre-wrap>Henry St &amp; Degraw St  </span> </td><td>Subscriber                                                         </td><td><span style=white-space:pre-wrap>Male  </span>                     </td><td>1987                                                               </td></tr>
	<tr><td>3945638                                                            </td><td>2017-05-08 19:47:18                                                </td><td>2017-05-08 19:59:01                                                </td><td> 703                                                               </td><td><span style=white-space:pre-wrap>Barrow St &amp; Hudson St  </span></td><td><span style=white-space:pre-wrap>W 20 St &amp; 8 Ave       </span> </td><td>Subscriber                                                         </td><td>Female                                                             </td><td>1986                                                               </td></tr>
	<tr><td>6208972                                                            </td><td>2017-06-21 07:49:16                                                </td><td>2017-06-21 07:54:46                                                </td><td> 329                                                               </td><td><span style=white-space:pre-wrap>1 Ave &amp; E 44 St        </span></td><td><span style=white-space:pre-wrap>E 53 St &amp; 3 Ave       </span> </td><td>Subscriber                                                         </td><td><span style=white-space:pre-wrap>Male  </span>                     </td><td>1992                                                               </td></tr>
	<tr><td>1285652                                                            </td><td>2017-02-22 18:55:24                                                </td><td>2017-02-22 19:12:03                                                </td><td> 998                                                               </td><td><span style=white-space:pre-wrap>State St &amp; Smith St    </span></td><td><span style=white-space:pre-wrap>Bond St &amp; Fulton St   </span> </td><td>Subscriber                                                         </td><td><span style=white-space:pre-wrap>Male  </span>                     </td><td>1986                                                               </td></tr>
</tbody>
</table>




```R
head(wash)
```


<table>
<thead><tr><th scope=col>X</th><th scope=col>Start.Time</th><th scope=col>End.Time</th><th scope=col>Trip.Duration</th><th scope=col>Start.Station</th><th scope=col>End.Station</th><th scope=col>User.Type</th></tr></thead>
<tbody>
	<tr><td>1621326                                                                                        </td><td>2017-06-21 08:36:34                                                                            </td><td>2017-06-21 08:44:43                                                                            </td><td> 489.066                                                                                       </td><td><span style=white-space:pre-wrap>14th &amp; Belmont St NW                       </span>        </td><td><span style=white-space:pre-wrap>15th &amp; K St NW                                     </span></td><td>Subscriber                                                                                     </td></tr>
	<tr><td> 482740                                                                                        </td><td>2017-03-11 10:40:00                                                                            </td><td>2017-03-11 10:46:00                                                                            </td><td> 402.549                                                                                       </td><td><span style=white-space:pre-wrap>Yuma St &amp; Tenley Circle NW                 </span>        </td><td><span style=white-space:pre-wrap>Connecticut Ave &amp; Yuma St NW                       </span></td><td>Subscriber                                                                                     </td></tr>
	<tr><td>1330037                                                                                        </td><td>2017-05-30 01:02:59                                                                            </td><td>2017-05-30 01:13:37                                                                            </td><td> 637.251                                                                                       </td><td><span style=white-space:pre-wrap>17th St &amp; Massachusetts Ave NW             </span>        </td><td><span style=white-space:pre-wrap>5th &amp; K St NW                                      </span></td><td>Subscriber                                                                                     </td></tr>
	<tr><td> 665458                                                                                        </td><td>2017-04-02 07:48:35                                                                            </td><td>2017-04-02 08:19:03                                                                            </td><td>1827.341                                                                                       </td><td><span style=white-space:pre-wrap>Constitution Ave &amp; 2nd St NW/DOL           </span>        </td><td><span style=white-space:pre-wrap>M St &amp; Pennsylvania Ave NW                         </span></td><td><span style=white-space:pre-wrap>Customer  </span>                                             </td></tr>
	<tr><td>1481135                                                                                        </td><td>2017-06-10 08:36:28                                                                            </td><td>2017-06-10 09:02:17                                                                            </td><td>1549.427                                                                                       </td><td>Henry Bacon Dr &amp; Lincoln Memorial Circle NW                                                </td><td><span style=white-space:pre-wrap>Maine Ave &amp; 7th St SW                              </span></td><td>Subscriber                                                                                     </td></tr>
	<tr><td>1148202                                                                                </td><td>2017-05-14 07:18:18                                                                    </td><td>2017-05-14 07:24:56                                                                    </td><td> 398.000                                                                               </td><td><span style=white-space:pre-wrap>1st &amp; K St SE                              </span></td><td>Eastern Market Metro / Pennsylvania Ave &amp; 7th St SE                                </td><td>Subscriber                                                                             </td></tr>
</tbody>
</table>




```R
head(chi)
```


<table>
<thead><tr><th scope=col>X</th><th scope=col>Start.Time</th><th scope=col>End.Time</th><th scope=col>Trip.Duration</th><th scope=col>Start.Station</th><th scope=col>End.Station</th><th scope=col>User.Type</th><th scope=col>Gender</th><th scope=col>Birth.Year</th></tr></thead>
<tbody>
	<tr><td>1423854                                                                  </td><td>2017-06-23 15:09:32                                                      </td><td>2017-06-23 15:14:53                                                      </td><td> 321                                                                     </td><td><span style=white-space:pre-wrap>Wood St &amp; Hubbard St         </span></td><td><span style=white-space:pre-wrap>Damen Ave &amp; Chicago Ave     </span> </td><td>Subscriber                                                               </td><td><span style=white-space:pre-wrap>Male  </span>                           </td><td>1992                                                                     </td></tr>
	<tr><td> 955915                                                              </td><td>2017-05-25 18:19:03                                                  </td><td>2017-05-25 18:45:53                                                  </td><td>1610                                                                 </td><td><span style=white-space:pre-wrap>Theater on the Lake          </span></td><td>Sheffield Ave &amp; Waveland Ave                                     </td><td>Subscriber                                                           </td><td>Female                                                               </td><td>1992                                                                 </td></tr>
	<tr><td><span style=white-space:pre-wrap>   9031</span>                          </td><td>2017-01-04 08:27:49                                                      </td><td>2017-01-04 08:34:45                                                      </td><td> 416                                                                     </td><td><span style=white-space:pre-wrap>May St &amp; Taylor St           </span></td><td><span style=white-space:pre-wrap>Wood St &amp; Taylor St         </span> </td><td>Subscriber                                                               </td><td><span style=white-space:pre-wrap>Male  </span>                           </td><td>1981                                                                     </td></tr>
	<tr><td> 304487                                       </td><td>2017-03-06 13:49:38                           </td><td>2017-03-06 13:55:28                           </td><td> 350                                          </td><td>Christiana Ave &amp; Lawrence Ave             </td><td>St. Louis Ave &amp; Balmoral Ave              </td><td>Subscriber                                    </td><td><span style=white-space:pre-wrap>Male  </span></td><td>1986                                          </td></tr>
	<tr><td><span style=white-space:pre-wrap>  45207</span>                          </td><td>2017-01-17 14:53:07                                                      </td><td>2017-01-17 15:02:01                                                      </td><td> 534                                                                     </td><td><span style=white-space:pre-wrap>Clark St &amp; Randolph St       </span></td><td>Desplaines St &amp; Jackson Blvd                                         </td><td>Subscriber                                                               </td><td><span style=white-space:pre-wrap>Male  </span>                           </td><td>1975                                                                     </td></tr>
	<tr><td>1473887                                                                 </td><td>2017-06-26 09:01:20                                                     </td><td>2017-06-26 09:11:06                                                     </td><td> 586                                                                    </td><td>Clinton St &amp; Washington Blvd                                        </td><td><span style=white-space:pre-wrap>Canal St &amp; Taylor St        </span></td><td>Subscriber                                                              </td><td><span style=white-space:pre-wrap>Male  </span>                          </td><td>1990                                                                    </td></tr>
</tbody>
</table>



### Question 1


**Your question 1 goes here.**


```R
What's the common month?
```


```R
library(readr);
library(tidyr);
library(plyr)
library(dplyr);
library(ggplot2)
```

    
    Attaching package: ‘dplyr’
    
    The following objects are masked from ‘package:plyr’:
    
        arrange, count, desc, failwith, id, mutate, rename, summarise,
        summarize
    
    The following objects are masked from ‘package:stats’:
    
        filter, lag
    
    The following objects are masked from ‘package:base’:
    
        intersect, setdiff, setequal, union
    



```R
chi <- read.csv('chicago.csv')
ny <- read.csv('new_york_city.csv')
wash <- read.csv('washington.csv')
```


```R
chi$Start.Month <- format(as.Date(chi$Start.Time), '%m')
ny$Start.Month <- format(as.Date(ny$Start.Time), '%m')
wash$Start.Month <- format(as.Date(wash$Start.Time), '%m')
```


```R
month.sum <- function(x){
    df <- x %>% group_by(month=x$Start.Month) %>% filter(!is.na(month)) %>% summarise(mon.count=n())
    return(df)
}
chi_month <- month.sum(chi)
chi_month
ny_month <- month.sum(ny)
ny_month
wash_month <- month.sum(wash)
wash_month
```


<table>
<thead><tr><th scope=col>month</th><th scope=col>mon.count</th></tr></thead>
<tbody>
	<tr><td>01  </td><td> 650</td></tr>
	<tr><td>02  </td><td> 930</td></tr>
	<tr><td>03  </td><td> 803</td></tr>
	<tr><td>04  </td><td>1526</td></tr>
	<tr><td>05  </td><td>1905</td></tr>
	<tr><td>06  </td><td>2816</td></tr>
</tbody>
</table>




<table>
<thead><tr><th scope=col>month</th><th scope=col>mon.count</th></tr></thead>
<tbody>
	<tr><td>01   </td><td> 5745</td></tr>
	<tr><td>02   </td><td> 6364</td></tr>
	<tr><td>03   </td><td> 5820</td></tr>
	<tr><td>04   </td><td>10661</td></tr>
	<tr><td>05   </td><td>12180</td></tr>
	<tr><td>06   </td><td>14000</td></tr>
</tbody>
</table>




<table>
<thead><tr><th scope=col>month</th><th scope=col>mon.count</th></tr></thead>
<tbody>
	<tr><td>01   </td><td> 8946</td></tr>
	<tr><td>02   </td><td>11563</td></tr>
	<tr><td>03   </td><td>12612</td></tr>
	<tr><td>04   </td><td>18522</td></tr>
	<tr><td>05   </td><td>17072</td></tr>
	<tr><td>06   </td><td>20335</td></tr>
</tbody>
</table>




```R
df <- data.frame(Month=chi_month$month, Chicago=chi_month$mon.count, New_York=ny_month$mon.count, Washington=wash_month$mon.count)
df
```


<table>
<thead><tr><th scope=col>Month</th><th scope=col>Chicago</th><th scope=col>New_York</th><th scope=col>Washington</th></tr></thead>
<tbody>
	<tr><td>01   </td><td> 650 </td><td> 5745</td><td> 8946</td></tr>
	<tr><td>02   </td><td> 930 </td><td> 6364</td><td>11563</td></tr>
	<tr><td>03   </td><td> 803 </td><td> 5820</td><td>12612</td></tr>
	<tr><td>04   </td><td>1526 </td><td>10661</td><td>18522</td></tr>
	<tr><td>05   </td><td>1905 </td><td>12180</td><td>17072</td></tr>
	<tr><td>06   </td><td>2816 </td><td>14000</td><td>20335</td></tr>
</tbody>
</table>




```R
newdf <- df %>% gather(key=City, value=Count, Chicago, New_York, Washington)
newdf
```


<table>
<thead><tr><th scope=col>Month</th><th scope=col>City</th><th scope=col>Count</th></tr></thead>
<tbody>
	<tr><td>01        </td><td>Chicago   </td><td>  650     </td></tr>
	<tr><td>02        </td><td>Chicago   </td><td>  930     </td></tr>
	<tr><td>03        </td><td>Chicago   </td><td>  803     </td></tr>
	<tr><td>04        </td><td>Chicago   </td><td> 1526     </td></tr>
	<tr><td>05        </td><td>Chicago   </td><td> 1905     </td></tr>
	<tr><td>06        </td><td>Chicago   </td><td> 2816     </td></tr>
	<tr><td>01        </td><td>New_York  </td><td> 5745     </td></tr>
	<tr><td>02        </td><td>New_York  </td><td> 6364     </td></tr>
	<tr><td>03        </td><td>New_York  </td><td> 5820     </td></tr>
	<tr><td>04        </td><td>New_York  </td><td>10661     </td></tr>
	<tr><td>05        </td><td>New_York  </td><td>12180     </td></tr>
	<tr><td>06        </td><td>New_York  </td><td>14000     </td></tr>
	<tr><td>01        </td><td>Washington</td><td> 8946     </td></tr>
	<tr><td>02        </td><td>Washington</td><td>11563     </td></tr>
	<tr><td>03        </td><td>Washington</td><td>12612     </td></tr>
	<tr><td>04        </td><td>Washington</td><td>18522     </td></tr>
	<tr><td>05        </td><td>Washington</td><td>17072     </td></tr>
	<tr><td>06        </td><td>Washington</td><td>20335     </td></tr>
</tbody>
</table>




```R
common_month_plot <- ggplot(newdf, aes(City, Count, fill=Month)) + geom_col(position = "dodge") + ggtitle('Months for each City') + theme(plot.title = element_text(hjust = 0.5))
```


```R
common_month_plot
```


![png](output_14_0.png)



```R
mean_june <- mean(c(df[6,2],df[6,3],df[6,4]))
mean_june
```


12383.6666666667


**Summary of your question 1 results goes here.**


```R
From the above bar plot, we can conculde that the common month for all three cities is June with 2816 for Chicago, 14000 for NYC, and 20335 for Washinfton. Mean of common month is 12383.7 
```

### Question 2

**Your question 2 goes here.**


```R
What's the average travel time in all the three cities
```


    Error in parse(text = x, srcfile = src): <text>:1:5: unexpected INCOMPLETE_STRING
    1: What's the average travel time in all the three cities
            ^
    Traceback:




```R
ny = read.csv('new_york_city.csv')
wash = read.csv('washington.csv')
chi = read.csv('chicago.csv')
```


```R
library(readr);
library(tidyr);
library(plyr);
library(dplyr);
library(ggplot2)
```


```R
trip_dur <- list(chi$Trip.Duration, ny$Trip.Duration[!is.na(ny$Trip.Duration)], wash$Trip.Duration[!is.na(wash$Trip.Duration)]) 
avg_trip <- lapply(trip_dur, mean)
avg_trip
```


<ol>
	<li>937.172769409038</li>
	<li>903.614690792237</li>
	<li>1233.95333709152</li>
</ol>




```R
df <- data.frame(City=c('Chicago', 'New_York', 'Washington'), avg_trip=c(avg_trip[[1]],avg_trip[[2]],avg_trip[[3]]))
```


```R
ggplot(df, aes(City, avg_trip, fill=City)) + geom_col(position='dodge') + geom_point(alpha=0.5) + ggtitle('Average Travel Time') + theme(plot.title = element_text(hjust = 0.5))
```


![png](output_24_0.png)



```R
In sum, average trip timr in Washington is the highest amoung all three cities.And mean of Chicago and NYC is similar, which is around 900
```


    Error in parse(text = x, srcfile = src): <text>:1:4: unexpected symbol
    1: In sum
           ^
    Traceback:



**Summary of your question 2 results goes here.**

### Question 3

**Your question 3 goes here.**


```R
What are the counts of each gender (only available for NYC and Chicago)?
```


```R
ny <- read.csv('new_york_city.csv')
chi <- read.csv('chicago.csv')
```


```R
library(readr);
library(tidyr);
library(dplyr);
library(ggplot2)
```


```R
gender_ct_chi <- chi %>% group_by(Gender) %>% summarize(chi.gender.ct=n())
gender_ct_chi
gender_ct_ny <- ny %>% group_by(Gender) %>% summarize(ny.gender.ct=n())
gender_ct_ny
```


<table>
<thead><tr><th scope=col>Gender</th><th scope=col>chi.gender.ct</th></tr></thead>
<tbody>
	<tr><td>      </td><td>1748  </td></tr>
	<tr><td>Female</td><td>1723  </td></tr>
	<tr><td>Male  </td><td>5159  </td></tr>
</tbody>
</table>




<table>
<thead><tr><th scope=col>Gender</th><th scope=col>ny.gender.ct</th></tr></thead>
<tbody>
	<tr><td>      </td><td> 5410 </td></tr>
	<tr><td>Female</td><td>12159 </td></tr>
	<tr><td>Male  </td><td>37201 </td></tr>
</tbody>
</table>




```R
df <- data.frame(Gender=c('Unkown', 'Female', 'Male'), NYC=gender_ct_ny$ny.gender.ct, Chicago=gender_ct_chi$chi.gender.ct)
newdf <- df %>% gather(key=City, value=Count, NYC, Chicago)
```


```R

```


![png](output_33_0.png)



```R
ggplot(newdf, aes(City, Count, fill=Gender)) + geom_col(position='dodge', alpha=0.5, colour="black") + ggtitle('Gender by Cities') + theme(plot.title = element_text(hjust = 0.5))
```


![png](output_34_0.png)



```R
The result is obviously contrasting, the common feature in two cities is that the number of identified male is larger than that of female significantly with reported 37201 males in NYC.
```


    Error in parse(text = x, srcfile = src): <text>:1:5: unexpected symbol
    1: The result
            ^
    Traceback:



**Summary of your question 3 results goes here.**


## Finishing Up

> Congratulations!  You have reached the end of the Explore Bikeshare Data Project. You should be very proud of all you have accomplished!

> **Tip**: Once you are satisfied with your work here, check over your report to make sure that it is satisfies all the areas of the [rubric](https://review.udacity.com/#!/rubrics/2508/view). 


## Directions to Submit

> Before you submit your project, you need to create a .html or .pdf version of this notebook in the workspace here. To do that, run the code cell below. If it worked correctly, you should get a return code of 0, and you should see the generated .html file in the workspace directory (click on the orange Jupyter icon in the upper left).

> Alternatively, you can download this report as .html via the **File** > **Download as** submenu, and then manually upload it into the workspace directory by clicking on the orange Jupyter icon in the upper left, then using the Upload button.

> Once you've done this, you can submit your project by clicking on the "Submit Project" button in the lower right here. This will create and submit a zip file with this .ipynb doc and the .html or .pdf version you created. Congratulations!


```R
system('python -m nbconvert Explore_bikeshare_data.ipynb')
```
