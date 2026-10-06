# Rule-Based Health & Nutrition Expert System (Experta)

A rule-based expert system that classifies a person's BMI, asks about their activity level, and recommends a diet and a health diagnosis. University project for the Expert Systems course (Arab International University).

## How it works

The system uses **forward chaining** with the [Experta](https://github.com/nilp0inter/experta) framework (a Python implementation of CLIPS-style production rules):

1. **Start rule** (highest salience): asks for weight (kg) and height (m), then calculates BMI
2. **Classification rules**: put the person in one of four BMI categories (Underweight, Normal, Overweight, Obese) and set a matching diet
3. **Activity rule**: asks for the activity level (`high`, `moderate`, `low`, `sedentary`) and keeps asking until the input is valid
4. **Diagnosis rules**: combine BMI category and activity level into a diagnosis
5. **Recommendation rule** (lowest salience): prints the recommended diet
6. **Restart loop**: the user can run the system again until they are satisfied

Rule priority is controlled with **salience**, so the rules always fire in the right order.

## Example diagnoses

| BMI category | Activity | Diagnosis |
|--------------|----------|-----------|
| Underweight | high / moderate | Active Underweight |
| Normal | high | Healthy Lifestyle |
| Normal | not high | Improve Activity |
| Overweight | low | High Risk Overweight |
| Obese | sedentary | Severe Risk |

(The notebook contains the full rule set.)

## Run it

```bash
pip install experta jupyter
jupyter notebook expert_system.ipynb
```

Run the cell and answer the prompts in the notebook. Note: `experta` may need a compatible Python version (3.9 or 3.10 works best).

> Educational project only. It is not medical advice.
