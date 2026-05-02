# heartDiseaseV2

Simple Flask app for heart disease risk prediction using `heart_model_rf500.joblib`.

## Files
- `app.py` - Flask app and prediction endpoints
- `templates/index.html` - web form
- `heart_model_rf500.joblib` - trained model
- `Dockerfile` - container setup
- `requirements.txt` - Python dependencies

## Run locally
```bash
pip install -r requirements.txt
cp .env.example .env
# edit .env and set OPENAI_API_KEY
python app.py
```

Open `http://127.0.0.1:1111`.

`OPENAI_MODEL` is optional and defaults to `gpt-4o-mini`.

## Docker
```bash
docker build -t heartDiseaseV2 .
docker run -p 1111:1111 -e OPENAI_API_KEY="your-api-key" heartDiseaseV2
```

## API
`POST /api/predict` with JSON body:
```json
{
  "Age": 55,
  "Sex": "M",
  "ChestPainType": "ATA",
  "RestingBP": 130,
  "Cholesterol": 250,
  "FastingBS": 0,
  "RestingECG": "Normal",
  "MaxHR": 150,
  "ExerciseAngina": "N",
  "Oldpeak": 1.2,
  "ST_Slope": "Flat"
}
```

## Note
The model was trained with scikit-learn 1.6.1, so the Docker image pins the same version.

The assistant uses OpenAI when `OPENAI_API_KEY` is set. Without the key, it falls back to local rule-based answers.
