# SAMueL Advisory Group November 2022

## Attendees (initials) - Introductions

* Ajay Bhalla (AB) (chair) - Stroke consultant, Guys & St Thomas hospital. Work on SSNAP.
* Gary Ford (GF) - Academic stroke physician, Oxford. Executive of AHSN.
* Martin Utley (MU) - Operational researcher, UCL. Modelled patient flow in stroke pathways in North-Central London, advising capacity allocation along the pathway (hyper acute, acute & enhanced supported discharge). 
* Martin James (MJ) - Investigator on SAMueL2 project. Stroke physician, RD&E. Work on SSNAP.
* Keira Pratt-Boyden (KPB) - Qualitative researcher on SAMueL2 project.
* Mike Allen (MA) - Modeller data scientist, co-lead the SAMueL2 project with Martin James.
* Kerry Pearn (KP) (note-taker) - Modeller. Focusing on the explainable machine learning part.


## Key points

* The advisory group were enthusiastic about, and supportive of, the project.

### Modelling

#### Summary of presentation

* The SAMUeL-1 model was described as answering three questions:

    1. What if processes were faster (door-to-needle 30 minutes)?
    2. What if we know more onset times (use national upper quartile level)?
    3. What if decision making at the hospital is like that of a benchmark set of hospitals (benchmark hospitals are the top 30 thrombolysisng hospitals when thrombolysis rate predicted using a standard 10k cohort of patients passed to all hospital models).?
    
* The SAMueL analysis uses a hospital's own patient population as the basis of examining the 'what if?' scenarios.

* SAMuel-1 analysis predicts thrombolysis rates could average 18-19% with the changes investigated.

* SAMueL-2 modelling expands on SAMueL-1 modelling in various ways:

    1. We are building 'Explainable machine learning' models
    2. We will de-anonymise hopsitals
    3. We will check that higher thrombolysing hospitals do not have significant risk of worsened outcomes
    4. We will incorporate ambulance times into pathway model
    5. We will link to SSNAP organisational audit data
    6. We will build Health Economics models
    
* Progress on 'Explainable machine learning' model:

    1. We have switched to XGBoost as the main model type
    2. The model can be simplified from 61 features to 8 features with little loss in accuracy (ROC 0.916 vs. 0.921). After discussion with stroke docs at Exeter, we have subsequently increased this model to 10 features (ROC 0.918) so that age is included, as age was a matter of discussion among the docs.
    3. We have built a SHAP (Shapley Additive Values) model to explain the predictions of the XGBoost model. The SHAP model explains predictions at an individual level, and these may be combined to show behaviour of the model at a population level.
    4. The SHAP value can isolate the effect of a hospital on prediction to thrombolyse.
    5. We have created artificial patients to show differences in clinical decision-making (e.g. mild stroke, or previous disability, or estimated stroke onset time).

* HQIP request for SAMueL-2 data set has been submitted.
           
#### Points of discussion

* Why are some hospitals more cautious?
* Do you get more thrombolysis in patients where there is longer to consider the decision?
* Do units with more admissions give more thrombolysis?
* Do you get a higher precisely known stroke onset time for patients arriving earlier?
* Do different hospitals have different attitudes to patients age 80+ who would be given thrombolysis in the 3.0 to 4.5 hour window?
* 20% thrombolysis in an arbitrary target - we need to tailor it to hospitals (but beware hospitals considering that they just can't give thrombolysis to more patients).
* It will be v. interesting to see how organisational data may predict differences in thrombolysis
* Effect of pre-stroke disability on willingness to give thrombolysis known from previous work. As trials did not include patients with higher pre-stroke disability, there is a lack of data specifically supporting thrombolysis in these patients, so there is confusion about what to do.
* How much does time of day effect willingness to use thrombolysis?
* Martin Utley would be very happy to be involved in work helping to visualise the decision space.
* It will be good to include pre-hospital times in pathway model, as this has slowed as hospitals have got faster at thrombolysis (this will be in SAMueL-2 model).
* Need to consider how to share results where hospital is known (e.g. general paper/presentation output could anonymise hospital). Talk to stakeholders about how to share detailed hospital-level analysis (e.g just share locally?).

### Qualitative research

#### Summary of presentation

* Qualitative research in the planning and piloting stage (ethics submission due Jan 2023)
* Original methods have evolved, to include an ethnographic perspective, looking at connections within the system that may otherwise be missed, and looking at what is shared across the system, and what differs. This work will involve observation studies (fieldwork) at three hospitals.
* Research will look at two aspects of thrombolysis:
    1. General knowledge about how IVT is being delivered
    2. Current use of SSNAP by staff, and how SAMueL models may best have influence
* Key question: "What should a machine-learning model based on SNNAP data look like, do, and deliver, if it is to optimise improvement, and reduce unwarranted variation, in thrombolysis?"
* Research will use the NASSS ("Nonadoption, Abandonment, and Challenges to the Scale-Up, Spread, and Sustainability")framework.
* Three work packages within the qualitative work:
    1. Study of context to refine our ML approach (methods: focussed obs + semi structured ivs). This will involved 2 weeks observational work at each of three hopsitals.
    2. To improve our understanding of physicians’ and stroke care staffs’ attitudes and interpretations of information from the national stroke audit and to the use of ML to improve clinical decision-making (methods: focussed obs + semi structured ivs)
    3. ML testing and learning in order to understand the feasibility and usefulness of ML (methods: co-production workshops with stakeholders)


#### Points of discussion

* Important to use the qualitative research to maximise the potential of the modelling and machine-learning work
* Important to include nurses as well as docs, and to look at processes at different times of day and day of week, if possible
* There is probably more benefit to be had concentrating more work on lower thrombolysing hospitals, or those hospitals where the modelling predicts thrombolysis use could be significantly higher (we won't have that data until after the ethics application, but we can try and target such hospitals in informal stakeholder analysis). Tolstoy quote (from Anna Karenina): "All Happy families resemble one another, but each unhappy family is unhappy in its own way"
* Also consider units that may be over-thrombolysing
* NHS-England Communities of Practice of thrombolysis will identify 6-8 low thrombolysing sites
