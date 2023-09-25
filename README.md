# Pricing_Tool
Life Insurance Pricing Tool
1 Objective
To enhance sales processes, an insurer selling a variety of products intends to equip the front office
with a new pricing instrument. Although the present actuarial group has created a pricing tool,
it doesn’t fully meet the front office’s expectations. You can access the preliminary pricing tool
through the following link:
Preliminary Pricing Tool
The initial iteration of the pricing tool has been crafted by the actuarial team using the R software.
The tool’s construction involved the application of the shiny package during development and
the rsconnect package for deployment. At its current stage, this preliminary version does not
encompass the entirety of the insurer’s product range. In response, the front office has requisitioned
a more comprehensive rendition using the same software. Additionally, for the products within the
aforementioned link, the actuarial team used the AM92 Ultimate mortality table; however, this table
does not accurately reflect the mortality patterns of policyholders within the insurer’s portfolio.
As a consultant contracted by this insurer, your assignment entails the creation of an improved
iteration of the above preliminary tool. It must be designed using R and shiny, and it must have
the capability to present (i) the premium payable by the policyholder (either single or leveled), and
(ii) a graphical representation depicting the evolution of the reserve, and (iii) the numerical values
of the reserve at time 0, 1, 2, 3, T-1 and T, where T is the term of the policy (corresponding to
the maximum attainable age for life-long products). Users utilizing the pricing tool should be able
to select all the variables delineated within this document.
Your numerical output should reflect the specific mortality table assigned to your student number.
Your mortality table can be found in the following link:
Download your mortality table
ETC3530/ETC5353 - Assignment - Page 2 of 7
Note the following conventions:
• The insurer exclusively offers policies to individuals aged between 20 and 80 years old.
• The maximum attainable age is 100. That is, payments after that age are not possible.
• The minimum term for temporary products is 5 years.
• Actuarial quantities involving integrals must be approximated using the usual approximation
formulas (i.e. A¯
x ≈ (1+i)
1
2 Ax). Analogously, actuarial quantities at monthly frequency must
be approximated using their counterparts at yearly frequency.
• The values of interest rate and inflation rate should be in [0, 10%].
• The values of expenses and bonuses should be in [0, 50%].
• For consistency, the reserve at time T of policies with a survival benefit at maturity T is
calculated ‘before’ the survival benefit payment. For instance, for a T-year pure endowment
with survival benefit B, the reserve at time T is T V = B. This only applies to survival
benefits. Reserves are calculated ‘after’ the death benefit payment. That is, for a T-year
term assurance, the reserve at time T is T V = 0.
ETC3530/ETC5353 - Assignment - Page 3 of 7
2 Task
Minimum features:
The pricing tool that you propose must contain at least the following features:
• Single premium, or level annual premiums paid throughout the term,
• The policyholder can choose among a pure endowment, a term assurance or an endowment
assurance,
• The sum assured, which could be payable either at the end of the year of death or immediately
on death depending on what the user selects.
It should also be possible to select the term of the contract, the sum assured, and the interest
rate, where the range of interest rate is [0, 10%]. All values must be calculated using your specific
mortality table.
Premium frequency:
In the case of level premiums, the insurer aims to provide policyholders with the option to select
from two frequencies for premium payments, namely, annual and monthly payment schedules. For
both scenarios, only the yearly reserve is required.
Expenses:
One of the requested improvements of the tool given in the template consists in including the
expenses. The company wants the expenses to be set as follows:
• Initial expenses in percentage of the gross premium, applicable for both single and level
premiums.
• Premium expenses (excluding the first premium) in percentage of the gross premium, and
incurred as long as the premium is paid. For yearly premiums, expenses start the second
year. For monthly premiums, expenses start the second month. For single premiums, there
are no premium expenses.
• Claim expenses in percentage of the benefit amount.
The values of the percentages of expenses should be in the interval [0, 50%].
Expenses must be reflected in the values of the premium, in the graphical evolution of the reserve,
and in the tables containing the selected values of the reserve.
ETC3530/ETC5353 - Assignment - Page 4 of 7
Bonuses and inflation:
For both whole life and term assurances with payment either at the end of the year of death or
immediately on death, the insurer wants to include a simple bonus vesting at the start of each year
excluding the first year. For these products, the user of the tool should be able to select separately
the initial amount, as well as the rate of bonus for assurances. The range of values for the (simple)
rates of increase for all these products should be [0, 50%].
Additionally, the insurer wants to allow for inflation in the above products (whole life and term
assurances). Increases due to inflation must be incorporated using a compound rate, and apply
from the second year onward. Specifically, assuming the initial death benefit is B, the insurer
combines bonuses (at rate b pa) and inflation (at rate j pa) in the following way:
• the sum payable over (or at the end of) the first year is B,
• the sum payable over (or at the end of) the second year is (1 + j)B(1 + b),
• the sum payable over (or at the end of) the third year is (1 + j)
2B(1 + 2b),
• and so on,
Similarly to interest rate, the range of inflation rate is [0, 10%]. Note that inflation does not apply
to premiums.
Select Mortality:
Finally, the insurance company wants to be able to calculate all values using either Ultimate or
Select Mortality. The user of the tool should be able to select the type of mortality (Ultimate vs
Select). Recall that you must use the mortality table which is specific to your student number.
ETC3530/ETC5353 - Assignment - Page 5 of 7
3 Instructions
• This is an individual assignment, and it accounts for 20% of the total unit grade.
• R packages and generative AI can be used.
• Any suspicious resemblance between two assignments (particularly with past years’ assignments) will be investigated seriously, especially that you are given many resources and that
you are allowed to use generative AI.
• Submit a PDF file containing:
(a) your name and student number,
(b) a short text (NO MORE THAN 200 WORDS) describing the features of the pricing tool
and how to use it,
(c) the link to the shiny pricing tool,
• Separately, submit the R script containing the code used for designing the tool, in a ‘.R’
format, not in ‘.rmd’ or any other format. This assignment must be done using R and
shiny.
• There is a significant number of students in this unit. Thus, providing the grades may
take some time. Please help the teaching team by submitting your work according to these
instructions.
• Consultation times will be scheduled to provide support in R. Note that it is usually hard for
the teaching team to provide help when you send an R code by email, because it is necessary
to have some context and to test the code in order to identify potential issues. Thus, for a
more efficient feedback, it is strongly recommended to attend consultations.
• DO NOT FORGET TO DEPLOY YOUR SHINY APP USING THE PACKAGE
rsconnect. ONLY DEPLOYED APPS WILL BE GRADED!
4 Useful resources
The following resources are available on Moodle:
• shiny tutorial from an external source.
• PDF file on how to start using shiny from an external source.
• R coding resources for Life Insurance Mathematics, including a video on using R for annuities
and assurances and the associated ‘.R’ file, as well as a video on how to create a simple shiny
app (recorded in 2021).
ETC3530/ETC5353 - Assignment - Page 6 of 7
5 Suggested timeline
It is strongly recommended to read through the assignment and to set small and specific targets
with deadlines. Do not leave everything to the last week before submission. Always run each line
of code before running a full script, which will allow you to identify which line generates a potential
issue. If your shiny app does not run, check the intermediary steps. Finally, try to double-check
your numerical output when possible - it’s not because it appears on your shiny app that it is
correct!
There are many ways to proceed, but here is a suggestion for a plan – the main idea is to break
the assignment into intermediary steps.
Step 1: Review the material on how to use R.
Step 2: Write functions for the EPV of life annuities. Link them to assurances using the premium
conversion. Functions are useful because they will allow you to make your tool flexible for
different ages or interest rates.
Step 3: Extend Step 2 to temporary products.
Step 4: Using your EPV of annuities and assurances, build functions of premiums for different products or the minimum features.
Step 5: Review the material on how to build a shiny app.
Step 6: Build your shiny app block-by-block. For instance, start with the premium of an assurance
only for policyholders aged 25 but the interest rate can be selected. Then include age as an
input variable. Then add the term. And so on.
Step 7: Include the reserve plot, and then the table containing the selected reserve values.
Step 8: Include monthly premiums.
Step 9: Include expenses.
Step 10: Include bonuses and inflation – consider adding them one at a time.
Step 11: Add Select mortality.
Step 12: Double check some numerical values (e.g. using Excel).
Step 13: Deploy your app!
ETC3530/ETC5353 - Assignment - Page 7 of 7
6 Grading
• The details regarding the assessment of the tool are given in the table below. The full mark
is given when the numerical values appear, and are correct.
• Originality is taken into account for up to 10 points, with 0/10 if the layout of your tool
is similar to that of the template. Think of this tool as being presented to the manager of
the marketing team, or to a client, so make it user-friendly. Some desirable features include
hiding input variables which are not necessary for a given product (e.g. once you choose a
single life annuity, all inputs related to assurances and joint life products would disappear).
• The maximum number of points is 100.
• Late submission penalty: 2.5 points per-day for late submissions.
• You must use the mortality table associated with your student number, otherwise the output
will be considered incorrect.
• Only deployed shiny apps will be graded.
• Only assignments performed using R and shiny will be graded.
• You must submit your R script in ‘.R’ format.
Features Marks
Minimum features premiums and reserves 30
Increased frequency in premiums 5
Increased frequency in reserves 5
Expenses in premiums 10
Expenses in reserves 10
Bonuses and inflation in premiums 10
Bonuses and inflation in reserves 10
Select Mortality in premiums 10
Select Mortality in reserves 10
10 points for the originality (assignment total capped at 100)
