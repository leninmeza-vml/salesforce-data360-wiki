# Unify Your Data

## Learning Objectives

In this step, you’ll:

- Create an identity resolution ruleset.
- Validate the output data.

## Unify Your Data

Unifying data using identity resolution is an essential step in turning bits of data into deep insights. But to take advantage of identity resolution, you need to first define the rules that Data 360 uses to determine which records match and which bits of data are included in a customer’s unified profile.

When setting up a ruleset, you need to decide how data is matched and reconciled. This ensures confidence in the quality of your unified profile data, whether you prioritize high consolidation rates or take a more conservative approach. When rulesets are run, unified link objects act as a bridge between your source data and your unified profile data. This ensures that you can always track the origin of each piece of a unified profile back to its original source.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Learn more about data, identity, and how Data 360 delivers its insights in [Data and Identity in Data 360.](https://trailhead.salesforce.com/content/learn/modules/data-and-identity-in-salesforce-cdp)

## Create an Identity Resolution Ruleset

For this project, you create one ruleset that matches source records from the Individual object. Once rulesets are run, unified individual profiles are created, along with the Unified Individual object, unified link objects, and unified contact point objects.

1. From Data Cloud, select the **Identity Resolutions** tab and click **New**.
2. Select **Create New Ruleset** and click **Next**.
3. With the default Data Space selected, choose **Individual** from the Primary Data Model Object dropdown. Individual is also preselected in the next field.
4. Since you’re only running one ruleset in this practice org, keep the Ruleset Id blank and click **Next**.
5. Name the ruleset `Individual MatchCopiar`.
6. To reduce costs by limiting jobs, ensure that **Run jobs automatically** is disabled. Additionally, click the toggle for Use case sensitive matching to link Individual ID and Fully Qualified Key option to disable it.

<!--THE END-->

![Create a new ruleset name, description, and establish whether or not it will run automatically.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/unify-your-data/images/191a3610a5b3f49f0135335261215501_kix.7rp5cpvp2exc.jpg)

7. Click **Save**.

### Configure

Once saved, it’s time to configure your rules.

1. From the **Ruleset Properties** panel under Match Rules, click **Configure** (1).

<!--THE END-->

![Screenshot showing the location of the Configure button.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/unify-your-data/images/f40911f514860811555c2048ced9a779_kix.5ypvaj32ybnl.jpg)

2. Review the instructions to learn more about how match rules work and then click **Next**.
3. Click **Configure** to select your first match rule.
4. Select **Fuzzy Name and Normalized Address** and click **Next**.
5. Because some cities can be misspelled, change the Match Method for City from Exact to **Fuzzy - Medium Precision**.

<!--THE END-->

![Selection of Fuzzy- Medium Precision from the match method dropdown for city.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/unify-your-data/images/9d1ef0e2213681da7926accdf0cdd3ee_kix.krbhq3cvc0gv.jpg)

6. Click **Next**.
7. Click **Add Match Rule** to add another rule.
8. Select **Fuzzy Name and Normalized Phone and Normalized Email** and click **Next**.
9. To customize your rule and find more matches, let’s remove Last Name by clicking the trashcan ![“”](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/unify-your-data/images/e8e622f1c631432bc6c7ee4fe8fd8a99_kix.z9es0iflce5k.png).

<!--THE END-->

![Select trashcan for the Last Name row.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/unify-your-data/images/9b34563beb42771b0fdad6f41946eebd_kix.jah0ic0tdcr.jpg)

10. Click **Next**.
11. Once done, click **Save**.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Learn more about the difference between fuzzy and normalized data in [Default and Custom Match Rules](https://help.salesforce.com/s/articleView?id=data.c360_a_match_rules_criteria.htm&type=5).

### Review Reconciliation Rule Concepts

When matches are found for fields where it makes sense to have only one piece of data, such as a person’s first name, the reconciliation rule determines which record contributes a value to the First Name field in the unified profile. For example, suppose your source data includes three records with similar names associated with the same email address: Liz Berkeley, Elizabeth Berkeley, and Eliza Berkeley with email address, eberkeley@example.com. They’re matched through the Fuzzy Name and Normalized Email match rule. Data 360 creates one unified profile to store data from these matching records and it’s the reconciliation rule that tells Data 360 which first name to use for that record.

Since data from the source records isn’t altered, the unified link object links the unified profile to all three first names, but only one can be used as the “First Name” in the unified profile. If the reconciliation rule is set to Most Recent, then identity resolution uses the name from the source record that was updated most recently. In the example of an ID field, prioritizing ID values based on the object the ID came from, may help you standardize IDs in your unified profiles.

Data can be reconciled based on frequency of a value, recency, or based on the object it came from. If fields have similar data, such as an id, you’ll get a warning to select what source to use for the unified profile.

**Update Reconciliation Rules**

1. Click the **Warnings** tab on the right side of the page to address the warning about the reconciliation rule for Individual.Individual Id. You get a warning if you’re missing required fields, so review this section to make sure your mappings are complete.

<!--THE END-->

![Screenshot of open warnings in the warnings tab.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/unify-your-data/images/927dec5a587ed44586ffd0500186455d_kix.s0o9rkje26.png)

2. Click **Individual.Individual Id** to modify the Reconciliation Rules.

<!--THE END-->

![Reconciliation Rules.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/unify-your-data/images/156a2c32ac1f48249cdbce08812999b8_kix.6bjhi1g1xjji.jpg)

3. Select the checkbox next to **Individual ID** and then click **Update Selected** or click the field link
4. Disable the **Default Reconciliation Rule** (1) and then set the Field Reconciliation Rule to **Source Priority**.
5. Use the arrows (2) to ensure that the Contact\_Home object is first in priority, followed by the Lead\_Home object.

<!--THE END-->

![Screenshot of the appropriate setup of the Field Reconciliation Rule.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/unify-your-data/images/97403ee6687c66e701a6863771d5109c_kix.gb7vmakx4ol0.jpg)

6. Click **Save**.
7. Click **Run Ruleset** (1).

![Run Ruleset button highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/unify-your-data/images/f17764904d6e3083798bc2feb2cf9c4c_kix.c7kud9p1mi6i.jpg)

## Verify Your Work

Now that you have a ruleset, updated reconciliation rules, and ran your ruleset, check your work by clicking **Verify step to earn 100 points**. For this exercise, you check that the rule was set up correctly. You don't have to wait for identity resolution to run your ruleset before you check your work.

## Resources

- [*Salesforce Help*: About Identity Resolution](https://help.salesforce.com/s/articleView?id=data.c360_a_identity_resolution.htm&type=5)
- [*Trailhead*: Data and Identity in Data 360](https://trailhead.salesforce.com/content/learn/modules/data-and-identity-in-salesforce-cdp)

---

## Luego: Intenta Verify Step del paso anterior

Con el warning resuelto, intenta **Verify Step** del paso "Unify Your Data" nuevamente.

---

## Si ya pasaste al paso "Create an Insight", sigue estos pasos:

1. Ve a **Calculated Insights** → **New**
2. Selecciona **Calculated Insight** + **Use Visual Builder** → **Next**
3. Busca y selecciona **Unified Individual** → **Next**
4. Agrega **Join** → selecciona **Case** → **Apply**
5. Agrega **Aggregate** → Measures: **Count > Case Id**, Metric Name: `Count Case ID` → **Apply**
6. Agrega dimensiones: **Unified Individual Id** → `Unified Individual`, **Case Status** → `Case Status`, **Last Name** → `Last Name`
7. **Save and Run** → nombre: `Unified Individual Case Counts` → **Enable**
8. En la pestaña Calculated Insights → **Publish Now**
9. Espera a que el Status cambie a **Active**

¿En cuál de los dos pasos (Unify o Create Insight) estás intentando hacer el Verify?


Tu canvas se ve bien — ya tienes **Unified Individual → Join → Join → Join** creado automáticamente con Case. Ahora necesitas:

---

## Siguiente paso: Agregar el Aggregate

1. Clic en **Apply** primero para guardar el Join actual
2. Clic en el **+** que aparece junto al último **Join** (el de la derecha)
3. Selecciona **Aggregate**
4. En **Measures** → clic en **+**
   - Busca en la sección **Count** → selecciona **Case Id**
   - Clic **Next**
   - Metric Name: `Count Case ID`
   - Clic **Apply**

---

## Luego agregar Dimensions (3 en total)

**Dimensión 1:**
- Clic **+** bajo Dimensions
- Selecciona **Unified Individual Id** (fuente: Unified Individual)
- Next → Dimension Name: `Unified Individual` → **Apply**

**Dimensión 2:**
- Clic **+** bajo Dimensions
- Selecciona **Case Status**
- Next → Dimension Name: `Case Status` → **Apply**

**Dimensión 3:**
- Clic **+** bajo Dimensions
- Selecciona **Last Name**
- Next → Dimension Name: `Last Name` → **Apply**

---

## Guardar

1. Clic **Save and Run**
2. Nombre: `Unified Individual Case Counts` → **Next**
3. Schedule: **Not Scheduled** → **Enable**
4. En la pestaña Calculated Insights → **Publish Now**

¿Puedes hacer clic en **Apply** en el Join actual y luego en el **+** del último Join para agregar el Aggregate?


Tu Calculated Insight está perfectamente configurado:

- ✅ Status: **Active**
- ✅ Nombre: **Unified Individual Case Counts**
- ✅ Campos correctos: Unified Individual, Last Name, Count Case ID, Case Status

El Last Run Status dice **Pending**, lo cual es normal — está procesando. Solo necesitas **esperar unos minutos** a que cambie de Pending a completado.

Una vez que termine de procesar, haz clic en **Verify Step** para ganar los 100 puntos. No necesitas hacer nada más en este paso. ¿Quieres que te ayude con el siguiente paso del proyecto?
