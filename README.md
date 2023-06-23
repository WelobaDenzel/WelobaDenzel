### Hi there 👋

<!--
**WelobaDenzel/WelobaDenzel** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->



import spotipy

def get_current_track():
    """Gets the currently playing track from Spotify."""
    client = spotipy.Spotify(auth_token="YOUR_SPOTIFY_AUTH_TOKEN")
    track = client.current_user_playing_track()
    return track

def add_current_track_to_github():
    """Adds the currently playing track to GitHub."""
    repo = github.Repository("YOUR_GITHUB_USERNAME", "YOUR_REPO_NAME")
    commit_message = "Added current track to README."
    track = get_current_track()
    readme = repo.get_readme()
    readme_content = readme.content
    if track is not None:
        readme_content += "\n\n**Currently playing:**"
        readme_content += "\n```"
        readme_content += track["name"]
        readme_content += " by "
        readme_content += track["artists"][0]["name"]
        readme_content += "```"
    repo.update_readme(readme_content, commit_message)

if __name__ == "__main__":
    add_current_track_to_github()
