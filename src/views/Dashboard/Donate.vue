<!-- @format -->

<template>
	<v-container fluid class="fill-height user amber lighten-4 text-center">
		<v-row align="center" justify="center">
			<v-col cols="12" md="10" sm="8">
				<v-card min-height="65vh">
					<v-card-title>Ủng Hộ Nhà Phát Triển</v-card-title>

					<div class="content text-center pb-5">
						<v-container fluid>
							<v-row>
								<v-col cols="12">
									<v-row align="center" justify="center">
										<v-data-table
											:headers="headers"
											hide-default-header
											hide-default-footer
											:items="items"
											class="elevation-0 text-center table"
										>
											<template v-slot:[`item.value`]="{ item }">
												<span v-html="item.value"></span>
											</template>
										</v-data-table>
									</v-row>
								</v-col>
							</v-row>
						</v-container>
					</div>
				</v-card>
			</v-col>
		</v-row>
	</v-container>
</template>

<script>
	import { mapState } from 'vuex'

	export default {
		name: 'Donate',
		computed: {
			...mapState(['user']),
		},
		data() {
			return {
				headers: [
					{
						value: 'name',
					},
					{
						value: 'value',
					},
				],
				items: [
					{
						name: 'Ngân Hàng MB Bank: ',
						value: '123 <br> ',
					},
				],
			}
		},
	}
</script>

<style lang="scss" scoped>
	.user {
		height: 91.5vh;
	}

</style>
