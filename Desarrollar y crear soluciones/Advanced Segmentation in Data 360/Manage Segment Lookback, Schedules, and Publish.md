# Manage Segment Lookback, Schedules, and Publish

## Learning Objectives

*   Determine the optimal lookback window for a segment to balance data relevance with system performance.  
    
*   Modify standard and rapid publish intervals based on the urgency of the marketing campaign.  
    
*   Interpret publish status to confirm that segment membership has been recalculated successfully.  
    

## Why Lookback and Schedule Matter

Northern Trail Outfitters (NTO) built its spring campaign segments, refined them with Group, Rank, and Limit (GRL), vector filters, consent, and nested logic. Now it’s time to go live. Two settings control when and how a segment runs: the lookback window and the publish schedule.

The lookback window defines how far back Data 360 retrieves data when evaluating criteria. The publish schedule defines how often the segment runs and sends membership to activation targets. Both settings also affect consumption. A wider lookback means more data to process. A more frequent schedule means more compute cycles per day. Choose too wide or too often and you drive up costs. Choose too narrow or too infrequent and your segment misses relevant behavior or goes stale before the next campaign. Think of the lookback as the date filter on a report: It controls how far back the data goes. The publish schedule is how often that report reruns with fresh numbers.

## Lookback Windows

Lookback windows apply only to standard publish segments. They don’t apply to rapid or real-time segments. You set the lookback when you create the segment. The default is 90 days. You can set it up to 2 years (or up to 360 days depending on org settings). The lookback evaluates the Event timestamp field that you configure on the data stream and map to the data model object (DMO). Only records whose event timestamp falls within the lookback window are considered. NTO uses 90 days for the spring campaign so they capture everyone who purchased or engaged in the last quarter. A shorter lookback, such as 30 days, focuses on more recent behavior. A longer lookback, such as 12 months, helps find lapsed customers for a win-back campaign.

You can also set a different range inside a container. When the container specifies a narrower range, the container range takes precedence for that criteria. NTO applies this to the Sales Order container from Unit 2, setting the container lookback to 60 days while the overall segment uses 90. This means engagement activity from the full quarter still qualifies a customer, while only purchases from the last two months count toward the order filter.

**Tip:** Start with 90 days for “recent activity” campaigns. For win-back or lapsed segments, try 6 or 12 months. For a flash sale, a short lookback such as 7 or 30 days keeps the audience focused.

## Publish Schedule: Standard Versus Rapid

### Standard Publish

Standard Publish includes two options: Schedule or Manual.

*   Choose Schedule when you want to set the frequency (daily, weekly, or monthly), start date and time, and interval such as 12 hours or 24 hours for daily.  
    
*   Choose Manual when you want to publish on demand by selecting the Publish Now button. Segments with a preset schedule must also send an activation to a target.  
    

NTO schedules their spring campaign to publish every 24 hours to Marketing Cloud Engagement (MCE) so the email team always has a fresh list.

### Rapid Publish

When you create a segment, you can choose Rapid Publish for 1-hour or 4-hour refresh. Rapid segments use only the past 7 days of engagement data. You can only activate them to MCE and Cloud File Storage. You can create up to 20 rapid segments. You can’t switch from standard to rapid after creation. NTO considers rapid for a flash sale later in the season but uses standard for the main campaign since the company needs the full 90-day lookback.

With a 24-hour standard schedule, NTO’s email team starts every morning with a fresh audience list. If a flash sale comes up later, the company knows rapid publish is an option, with its tradeoffs already understood.

![Graphic describing how to choose between standard and rapid publishing.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/advanced-segmentation-in-data-360/manage-segment-lookback-schedules-and-publish/images/af559bc5b6c85e7fefe5a08e3f792cb4_kix.l32qpcrp7dep.png)

## Publish Status

After publishing, you can check the status per activation target in Publish History or the segment detail.

*   **Success:** This status means the target was published successfully.  
    
*   **Error:** This status means the target failed to publish. Check for activation target misconfiguration, permissions, or data issues.  
    
*   **Skipped:** This status means the target is temporarily delayed due to limits on simultaneous publishes. Data 360 attempts the next run automatically.  
    
*   **Publishing:** This status means the target is in progress. Last published data stays available until the new publish completes.  
    
*   **Deferred:** This status means the target’s publish time was delayed due to simultaneous publish limits.  
    
*   **Blank:** This status means the target was never published.  
    

Michelle checks Publish History after the first run. MCE shows Success. S3 shows Deferred because several other segments were published at the same time. Michelle waits for the next cycle, and it goes through. However, if the Error status remains in this situation, open the segment for details and fix the issue. You can always run Publish Now after resolving problems.

## What Gets Published and Where

When a segment publishes, audience membership writes to the segment membership DMO and sends it to your configured activation targets. What gets sent depends on the activation membership you set for each target. Michelle sends Email, First Name, and Segment ID to MCE for journeys. She sends a broader attribute set to S3 for the analytics team. Same segment, different attributes per target.

Each target type has a discrete refresh behavior: full refresh (all records) or incremental refresh (only changes since the last successful refresh). The first publish to a target is always a full refresh.

Same segment, two targets, different attributes. The email team gets names and addresses; the analytics team gets the full dataset. NTO runs one segment instead of two, cutting maintenance in half.

## Put It All Together

NTO’s spring campaign is live. Here’s its checklist.

*   Created segments with a 90-day lookback (60 days for the Sales Order container)  
    
*   Added activations for MCE (email) and S3 (analytics) with the right attributes  
    
*   Set a 24-hour publish schedule  
    
*   Checked Publish History after the first run to confirm Success  
    

Michele can now reach customers with surgical precision—whether she’s using a nested segment to maintain consent or a real-time publish to catch a hiker in the moment.

NTO can adjust the lookback or schedule as the campaign evolves. The spring catalog segment might need a shorter lookback for a flash sale. The Surprise and Delight segment might move to a weekly schedule after the initial push. With Data 360, you’re in control of when your segments run and when fresh membership reaches your activation targets.

Congratulations! You’ve officially leveled up your Data 360 toolkit. You now know how to choose segment types and activation targets, narrow audiences with containers and GRL, refine with vector filters, consent, and nested segments. You can also manage lookback, schedules, and publish. You have everything you need to build precise, well-timed audiences in Data 360.

## Resources

*   [_Salesforce Help_ : Manage Data 360 Segment Schedules](https://help.salesforce.com/s/articleView?id=data.c360_a_manage_segment_schedules.htm&type=5)
*   [_Salesforce Help_ : Segment Types and Statuses](https://help.salesforce.com/s/articleView?id=data.c360_a_segment_types_statuses.htm&type=5)
*   [_Salesforce Help_ : Increase Segment Refresh from Data 360 to the Activation Targets](https://help.salesforce.com/s/articleView?id=data.c360_a_rapid_segment_publish.htm&type=5)
*   [_Salesforce Help_ : Publish a Segment in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_publish_segment.htm&type=5)

## Preguntas

**Pregunta 1:** Configuras el lookback del segmento a 90 días y agregas un contenedor que usa un filtro de 60 días en la fecha de creación. ¿Qué rango usa Data 360 para los criterios de ese contenedor?

✅ **B — 60 days**

El documento lo confirma: *"When the container specifies a narrower range, the container range takes precedence for that criteria."* El contenedor con 60 días sobreescribe el lookback general de 90 días para esos criterios específicos.

---

**Pregunta 2:** ¿Qué debe tener un segmento antes de que un programa de publicación preestablecido pueda enviarlo a un activation target?

✅ **A — An activation**

El documento lo indica explícitamente: *"Segments with a preset schedule must also send an activation to a target."* Sin una activación configurada, el schedule no puede enviar la membresía del segmento a ningún destino.