# Refine Segments with Hierarchical Aggregation, Vector Filters, and Consent Rules

## Learning Objectives

*   Configure hierarchical aggregation for Account and Unified Account segments (B2B) and use Segment on Unified Household for B2C.  
    
*   Apply vector filters and calculated insights as segment criteria using containers and Group, Rank, and Limit.  
    
*   Integrate consent filters and nested segment logic to maintain compliance and improve development efficiency.  
    

## More Refinement Levers

Northern Trail Outfitters (NTO) narrowed down its Surprise and Delight segment to the top 5 customers per region with containers and Group, Rank, and Limit (GRL). But the team has more questions. Can they find customers interested in “hiking and camping” without relying on exact keywords? Can they use engagement scores to prioritize loyalty members? And how do they make sure every segment respects email consent?

This unit covers the remaining refinement levers: hierarchical aggregation, Segment On Unified Household, vector filters, calculated insights, consent, and nested segments. Each lever adds precision to the segments you already built.

## Hierarchical Aggregation (B2B)

Business-to-business (B2B) customers use hierarchical aggregation in Data 360. When you build a segment on Account or Unified Account and add a related attribute that supports aggregation, Data 360 displays a Hierarchical Aggregation option on the container. When you enable it, Data 360 rolls up data from child accounts to the parent. Instead of “this account’s revenue” you get “this account plus all its subsidiaries’ revenue.” Use it to target parent accounts whose combined opportunity value meets a threshold, or exclude a hierarchy when any entity has a high-priority open case. Add a filter where the parent account has no value to restrict to top-level parents only.

NTO is business-to-consumer (B2C), so it doesn’t use hierarchy for this campaign. But if your org runs account-based marketing, this is how you get the full picture across parent and child accounts.

## Segment on Unified Household (B2C)

NTO is building the Family Adventure promotion. The NTO team creates a segment with Segment On set to Unified Household and adds the following criteria.

*   At least two household members  
    
*   A total household spend over $500 in the last year  
    

The result targets families, not individuals. You can also combine this with GRL to cap how many households per region, if needed.

Choose Unified Household as Segment On when your campaign goal is household-level. The same refinement idea from account hierarchy applies here: you’re narrowing by family-level data, not just the single record.

## Vector Filters (Beta)

Michelle wants to find customers interested in “hiking and camping” for the spring catalog. The problem: Customer interest data is messy. Some records say “trail running shoes.” Others say “camping gear.” Exact keyword filters miss these variations. Michele knows she can use Vector Filters to find these lookalike audiences.

The “Is Similar To” operator uses natural language processing to find records whose content is semantically similar to your reference value. Michelle adds a vector filter on product interest: Is Similar To “hiking and camping.” Records about trail running shoes or camping gear qualify even if customers don’t use those exact words. You can add vector filters to the Include or Exclude tab, with up to 50 filters per tab. They work on direct attributes and related attributes. You can also review the count of similar values returned and their preview.

## Calculated Insights in Segments

NTO has an Engagement Score calculated insight in its org that’s built from email opens, clickthroughs, and purchase frequency over the past 12 months. NTO wants to provide its most engaged loyalty members the Surprise and Delight gifts so the gesture lands where it matters most. The team adds the Engagement Score to the Include tab, for example, Engagement Score above 75, and uses the score in the Rank and Limit tab to rank within each region. Most of the calculation runs outside the segment. The segment just consumes the result.

Check your attribute library for processed calculated insights, which display when your data model supports them.

## Consent in Segmentation

Before NTO sends anything, it needs to respect email preferences. NTO adds an Include filter for “Email Opt-In equals true” so the spring campaign and Surprise and Delight segments only reach people who agreed to email. NTO also adds an Exclude filter for “Promotions Opt-Out equals true.” Consent attributes can come from your CRM, a preference center, or the Privacy Data Model. Add them to Include or Exclude like any other attribute. Think of consent filters as the bouncer at the door: No matter how well someone qualifies, they don’t get in without the right pass.

With opt-in and opt-out filters in place, NTO knows every email it sends reaches someone who wants it. That protects the brand and keeps deliverability high.

## Nested Segments

NTO built a High-Value Customers segment for the waterfall in Unit 1. Now the team needs the same audience for the spring campaign email, but with consent filters added. Instead of rebuilding the same filter logic from scratch, the team nests the existing segment. They create a parent segment, Spring Campaign Email, that includes only records in the High-Value child segment and adds the consent filters from above. This way, the parent combines High-Value membership with consent in one place and any future change to the High-Value definition automatically carries over.

When you nest a segment, both parent and child must use the same Segment On. You choose one of the following publish behaviors.

*   **Last Published Membership:** This option reuses the child's last published snapshot and is good for performance.  
    
*   **Segment Criteria:** This option copies the child’s filters into the parent and is good when the child changes often. NTO uses Segment Criteria so any update to the High-Value definition flows into the parent on the next run.  
    

Be mindful of these constraints: you can’t nest dynamic segments or segments in error or inactive state. Each nested segment can have up to 50 filters per tab. With Segment Criteria, the child’s filters count toward that limit.

By nesting the High-Value segment into the spring campaign parent, NTO saves hours of manual work and ensures their filters stay consistent across all global campaigns. When the High-Value definition changes, every campaign that depends on it updates automatically.

## What Comes Next

You helped NTO refine its segments. NTO’s containers and GRL narrow the Surprise and Delight gifts. Vector filters find hiking-interest customers. Engagement scores prioritize the most active loyalty members. Consent keeps everything compliant. A nested segment reuses the High-Value definition. In the next unit, you help NTO set the lookback window and publish schedule so these segments can go live.

## Resources

*   [_Salesforce Help_ : Hierarchical Aggregation in Segment Filters](https://help.salesforce.com/s/articleView?id=data.c360_a_segmentation_b2b_hierarchical_aggregation.htm&type=5)
*   [_Salesforce Help_ : Use Vector Filters in Data 360 Segments (Beta)](https://help.salesforce.com/s/articleView?id=data.c360_a_add_vector_filters_segmentation.htm&type=5)
*   [_Salesforce Help_ : Calculated Insights in Segmentation](https://help.salesforce.com/s/articleView?id=data.c360_a_calculated_insights_in_segments.htm&type=5)
*   [_Salesforce Help_ : Using Consent Preferences in Segmentation](https://help.salesforce.com/s/articleView?id=data.c360_a_using_consent_preferences_in_segmentation.htm&type=5)

## Preguntas

Las respuestas son las mismas que en el documento anterior, ya que es el mismo quiz:

**Pregunta 1:** ¿Qué comportamiento de publicación anidada deben elegir para ejecuciones eficientes usando la última audiencia calculada del hijo?

✅ **B — Last Published Membership**

Reutiliza el último snapshot publicado del segmento hijo, lo que es ideal para rendimiento eficiente.

---

**Pregunta 2:** ¿Qué deben habilitar en el contenedor para incluir datos de cuentas hijas en un segmento B2B?

✅ **D — Enable Hierarchical Aggregation in the container.**

Permite consolidar datos de cuentas hijas hacia el padre, obteniendo el valor total de oportunidades de toda la jerarquía.