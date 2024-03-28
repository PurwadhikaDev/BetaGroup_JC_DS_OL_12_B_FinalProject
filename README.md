### Model Machine Learning Prediksi Kelayakan Air Minum ###

Model ini bertujuan untuk memprediksi kelayakan air minum berdasarkan berbagai parameter kualitas air yang diukur. Kualitas air minum sangat penting bagi kesehatan manusia, dan memiliki sistem/model yang mampu memprediksi kelayakan air minum dapat membantu dalam pengambilan keputusan yang tepat terkait dengan penyediaan sumber air minum yang aman dan berkualitas. Dataset yang digunakan dalam model ini terdiri dari berbagai parameter kualitas air, seperti pH, Sulfate, Hardness, Chloromines, Solid, Turbidity, Conductivity, Organic Carbon dan Trihalomethanes. Standar parameter yang digunakan dalam pemodelan ini adalah standar WHO.
Model ini merupakan model klasifikasi yang menggunakan Random Forest. Evaluation Metric yang digunakana hanya presisi saja karna tujuan dalam pemodelan ini adalah untuk memnimalkan `false positive` atau air yang sebenernya tidak layak tapi diprediksi layak. Hal ini tentunya akan sangat membahayakan kesehatan masyarakat apabila terdapat air yang tidak layak namun diprediski layak.
