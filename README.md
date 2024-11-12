# Reinforcement Learning-Enhanced Movie Recommendation System

This project implements a Movie Recommendation System utilizing various recommendation algorithms, including content-based, popularity-based, and collaborative filtering methods. It further enhances the recommendation pipeline using reinforcement learning, inspired by the Netflix research project InTune: Reinforcement Learning-based Data Pipeline Optimization for Deep Recommendation Models.
Overview

The InTuneRecSys project is a comprehensive approach to movie recommendations that combines traditional recommendation techniques with advanced optimization methods. By leveraging concepts from InTune, our system dynamically optimizes resource allocation across the recommendation pipeline, improving efficiency and reducing latency for real-time recommendations.
Key Concepts

The InTune project by Netflix addresses critical bottlenecks in data pipeline optimization for deep recommendation models (DLRMs). Netflix’s InTune employs a reinforcement learning (RL) agent to manage and optimize data pipeline configurations in real-time, distributing computational resources effectively across data ingestion stages. This approach mitigates common pipeline challenges, such as suboptimal CPU usage and latency from unbalanced workloads, by allowing the RL agent to adapt to changing demands in real-time.

In this project, we apply a similar RL-based pipeline optimization concept, focusing on:

    Dynamic Resource Allocation: An RL agent optimizes system resources, such as CPU count and batch size, to maintain efficient pipeline performance.
    Throughput Maximization: By tuning data-loading throughput and minimizing idle times, the recommendation engine provides timely suggestions for a seamless user experience.
    Efficiency: Inspired by InTune’s adaptive approach, our model delivers improved recommendation speeds by reducing pipeline latency and better utilizing computational resources.

Project Goals

    Implement a Robust Recommendation System: Use content-based, collaborative filtering, and popularity-based algorithms, with an ensemble model for more accurate recommendations.
    Reinforcement Learning-Enhanced Pipeline: Optimize the recommendation engine's resource usage by dynamically adjusting computational parameters, as inspired by Netflix's InTune approach.
    Showcase Various Recommendation Techniques: Evaluate each model’s performance and demonstrate the business impact of the RL-enhanced system over traditional approaches.

Dataset

The project uses the MovieLens dataset, which includes:

    Full Dataset: 45,000 movies, 26 million ratings from 270,000 users.
    Small Dataset: 9,000 movies, 100,000 ratings from 700 users.
