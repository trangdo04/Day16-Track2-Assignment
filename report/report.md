# Báo cáo ngắn

Em sử dụng phương án CPU fallback với instance **r5.2xlarge** do tài khoản AWS mới chưa có quota GPU nên không thể triển khai **g4dn.xlarge**.  
Kết quả benchmark cho thấy thời gian load data là **1.7879 giây**, thời gian training là **0.7979 giây**, và **best iteration = 18**.  
Mô hình đạt **AUC-ROC = 0.9408**, **Accuracy = 0.9983**, **F1-Score = 0.6332**, **Precision = 0.5093**, **Recall = 0.8367**.  
Các chỉ số này cho thấy mô hình có khả năng phát hiện gian lận khá tốt, đặc biệt là **recall cao**, phù hợp với bài toán fraud detection.  
Về hiệu năng suy luận, độ trễ cho **1 dòng dữ liệu là 0.5648 ms** và throughput đạt khoảng **1,465,515 dòng/giây**.  
So với phương án GPU dùng cho LLM, phương án CPU phù hợp hơn với bài toán ML truyền thống như **LightGBM** và không yêu cầu quota đặc biệt.  
Dù không chạy được mô hình lớn như Gemma/vLLM, phương án này vẫn đáp ứng tốt yêu cầu benchmark và triển khai hạ tầng của bài lab.