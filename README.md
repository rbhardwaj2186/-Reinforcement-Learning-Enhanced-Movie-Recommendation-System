📈 InTuneRecSys: Reinforcement Learning-Enhanced Movie Recommendation System

This repository contains a sophisticated movie recommendation engine leveraging reinforcement learning to optimize recommendation pipeline efficiency. Inspired by Netflix's research project InTune: Reinforcement Learning-based Data Pipeline Optimization for Deep Recommendation Models, InTuneRecSys enhances traditional recommendation models by implementing an RL-based pipeline optimization for real-time, dynamic resource allocation.
🚀 Project Overview

InTuneRecSys integrates traditional recommendation methods (content-based, popularity-based, and collaborative filtering) into an advanced pipeline that combines these models with reinforcement learning. The RL agent dynamically allocates computational resources, optimizing throughput and reducing latency, thus delivering high-quality recommendations efficiently.
Key Features

    Dynamic Resource Optimization: Inspired by Netflix’s InTune, an RL agent automatically adjusts CPU count, batch sizes, and other resources based on real-time pipeline performance, ensuring high throughput and low latency.
    Multi-Model Recommendation Engine: Incorporates content-based, collaborative filtering, and popularity-based recommendations, enhanced by ensemble learning.
    Personalized and Scalable: Uses the MovieLens dataset to provide personalized recommendations tailored to user preferences across a massive dataset of over 45,000 movies and 26 million ratings.

📊 Business Impact

The application of reinforcement learning to pipeline optimization in recommendation systems provides substantial business benefits:

    Improved User Satisfaction: By delivering faster, more relevant movie suggestions, InTuneRecSys can increase user engagement and satisfaction with content offerings.
    Operational Efficiency: Optimizing the pipeline's resource usage reduces idle time and maximizes throughput, lowering computational costs and enabling more scalable recommendation services.
    Enhanced Personalization: By combining multiple recommendation models and refining recommendations through RL optimization, InTuneRecSys offers a more personalized user experience, tailored to individual viewing preferences.
    Cost Savings: By utilizing system resources more efficiently, InTuneRecSys reduces overall computational costs, aligning with operational goals in large-scale recommendation engines.

🧠 Technical Details

This project builds on concepts from the Netflix InTune research paper:

    Reinforcement Learning-Driven Optimization: A reinforcement learning agent dynamically adjusts pipeline resources, mirroring InTune’s approach to balancing data-loading throughput with computational efficiency.
    Data Pipeline Optimization: Inspired by InTune’s findings, this project addresses data ingestion bottlenecks by managing CPU resources effectively, reducing latency, and increasing data throughput across various recommendation models.

Dataset

InTuneRecSys utilizes two datasets from MovieLens:

    Full Dataset: 45,000 movies, 26 million ratings, 270,000 users
    Small Dataset: 9,000 movies, 100,000 ratings, 700 users

The Full Dataset is used to build a generalized recommendation engine, while the Small Dataset supports more personalized models.
Algorithms Implemented

    Simple Recommender: Offers popular movies by vote count and rating, ideal for general recommendations.
    Content-Based Recommender: Suggests movies similar to a user-provided title, using metadata like genres, cast, and keywords.
    Collaborative Filtering: Utilizes Singular Value Decomposition (SVD) for personalized recommendations based on user preferences.
    Hybrid Model: Combines content-based and collaborative filtering for more accurate, personalized recommendations.
    RL-Enhanced Model: Reinforcement learning dynamically optimizes pipeline throughput, improving real-time recommendation delivery.

Key Metrics

    CPU & GPU Utilization: Measures the RL agent's efficiency in resource allocation, reducing idle times and optimizing resource distribution.
    Latency and Throughput: Evaluates the speed and performance of data-loading and processing in the recommendation pipeline.
    Prediction Quality: Assessed by Mean Squared Error (MSE) and Root Mean Squared Error (RMSE) for collaborative filtering and hybrid recommendations.

🔧 How to Run

    Clone the Repository:

git clone https://github.com/username/InTuneRecSys.git
cd InTuneRecSys

Install Dependencies: Ensure you have Python 3.x and install required packages.

pip install -r requirements.txt

Load Dataset:

    Download the MovieLens dataset and place it in the data/ directory.
    Ensure both movies_metadata.csv and ratings_small.csv are present.

Run the Notebook: Launch Jupyter Notebook or your preferred IDE to explore each recommendation model.

    jupyter notebook

    View Results: Each section in the notebook demonstrates the pipeline for each recommendation model, showing comparative results for different models and highlighting the RL agent’s improvements in throughput and efficiency.

🖥️ Sample Code

Here’s a snippet of the RL-enhanced recommendation function that dynamically adjusts resources based on movie preferences and system load:

def rl_improved_recommendations(title):
    agent = RLAgent()  # Initialize RL agent
    idx = indices[title]
    sim_scores = sorted(list(enumerate(cosine_sim[idx])), key=lambda x: x[1], reverse=True)[1:26]
    movie_indices = [i[0] for i in sim_scores]
    movies = smd.iloc[movie_indices][['title', 'vote_count', 'vote_average', 'year', 'description']]
    
    # RL optimization to dynamically adjust resources
    for _ in range(10):
        action = agent.select_action(state)  # Choose action based on state
        # Update CPU count, batch size, etc., based on the action taken
        state['cpu_count'] = max(1, state['cpu_count'] + action['cpu_increment'])
        state['batch_size'] = max(1, state['batch_size'] + action['batch_increment'])
    
    # Display top recommendations and resource optimization details
    return movies

📚 References

    Netflix InTune Research Paper: InTune: Reinforcement Learning-based Data Pipeline Optimization for Deep Recommendation Models
        This project draws heavily from Netflix's InTune research, where an RL agent optimizes data pipelines for deep learning recommendation models. We apply similar concepts to build a recommendation engine that is both efficient and adaptive to resource constraints, improving overall user experience with personalized and timely recommendations.
