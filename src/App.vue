<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
			<v-spacer />
			Waypoint showcase
			<v-spacer />
    </v-app-bar>

    <v-main class="mt-8">
			<v-row>
				<v-col cols="2">
					<v-col v-for="panel in panels" :key="panel.title">
						<h3>{{ panel.title }}</h3>
						<ul>
							<li v-for="item in panel.content" :key="item">{{ item }}</li>
						</ul>
					</v-col>
				</v-col>
				
				<v-col cols="10">
					<v-row class="text-center">
						<v-col>
							<v-btn color="primary">
								Import from .Doc
							</v-btn>
						</v-col>
					</v-row>

					<v-row class="d-flex align-center justify-center">
						<v-col xl="8" lg="8">
							<v-card-title>Module 1: Utilizing Vue for Waypoint Solutions</v-card-title>
							<v-expansion-panels>
								<v-expansion-panel v-for="(panel, index) in panels" :key="panel.title">
									<v-expansion-panel-header>
										Unit {{ index + 1 }}
										<v-text-field :value="panel.title" class="pl-8" />
									</v-expansion-panel-header>
									<v-expansion-panel-content>
										<v-list>
											<v-list-item v-for="item in panel.content" :key="item" class="font-italic">
												<v-text-field :value="item" />
											</v-list-item>
										</v-list>
										<v-btn style="width: 100%" color="green lighten-2" @click="panel.content.push('And another thing...')">+</v-btn>
									</v-expansion-panel-content>
								</v-expansion-panel>
							</v-expansion-panels>
						</v-col>

						<v-col xl="8" lg="8">
							<v-btn style="width: 100%" color="green lighten-2" @click="panels.push(panels[panels.length - 1])">+</v-btn>
						</v-col>
					</v-row>

					<v-row class="text-center">
						<v-col>
							<v-btn color="primary">
								Convert into .Doc and .YML
							</v-btn>
						</v-col>
					</v-row>
				</v-col>
			</v-row>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {
  },

  data: () => ({
    panels: [
			{
				title: "Use Vue to create tech solutions",
				content: [
					"Lorem ipsum dolor",
					"Sit amet terietur marmot",
					"possit materiar",
					"possit materiari",
					"quellem vin quot."
				]
			},
			{
				title: "Simplify work-intensive assignments",
				content: [
					"Lorem ipsum dolor",
					"Sit amet terietur marmot",
					"possit materiar",
					"possit materiari",
					"quellem vin quot."
				]
			},
			{
				title: "Understand file layout at a glance",
				content: [
					"Lorem ipsum dolor",
					"Sit amet terietur marmot",
					"possit materiar",
					"possit materiari",
					"quellem vin quot."
				]
			},
			{
				title: "Suggest time-saving alternatives",
				content: [
					"Lorem ipsum dolor",
					"Sit amet terietur marmot",
					"possit materiar",
					"possit materiari",
					"quellem vin quot."
				]
			}
		]
  }),
};
</script>
