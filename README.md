Model Machine Learning Prediksi Kelayakan Air Minum 
Deskripsi Model
Model ini bertujuan untuk memprediksi kelayakan air minum berdasarkan berbagai parameter kualitas air yang diukur. Kualitas air minum sangat penting bagi kesehatan manusia, dan memiliki sistem yang mampu memprediksi kelayakan air dapat membantu dalam pengambilan keputusan yang tepat terkait dengan penyediaan sumber air minum yang aman dan berkualitas.

Dataset
Dataset yang digunakan dalam proyek ini terdiri dari berbagai parameter kualitas air, seperti pH, Sulfate, Hardness, Chloromines, Solid, Turbidity, Conductivity, Organic Carbon dan Trihalomethanes. Data tersebut telah dikumpulkan dari berbagai sumber dan telah diproses sebelumnya untuk analisis.

Model Machine Learning
Model ini merupakan model klasifikasi yang menggunakan Random Forest. Evaluation Metric yang digunakana hanya presisi saja karna tujuan dalam pemdelan ini adalah untuk memnimalkan `false positive` atau air yang sebenernya tidak layak tapi diprediksi layak. Hal ini tentunya
akan sangat membahayakan kesehatan masyarakat apabila terdapat false positve .
