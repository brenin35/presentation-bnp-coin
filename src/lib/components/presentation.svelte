<script lang="ts">
	import Code from './code.svelte';
	import Slide from './slide.svelte';

	const technologies = [
		{
			name: 'Svelte',
			logo: 'https://raw.githubusercontent.com/sveltejs/branding/master/svelte-logo.svg',
			description: 'Framework reativo e compilador'
		},
		{
			name: 'SvelteKit',
			logo: 'https://raw.githubusercontent.com/sveltejs/branding/master/svelte-logo.svg',
			description: 'Full-stack framework'
		},
		{
			name: 'TailwindCSS',
			logo: 'https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Tailwind_CSS_Logo.svg/2560px-Tailwind_CSS_Logo.svg.png',
			description: 'Utility-first CSS'
		},
		{
			name: 'Drizzle ORM',
			logo: 'https://pic.vsixhub.com/22/91/rphlmr.vscode-drizzle-orm-logo.webp',
			description: 'Type-safe ORM'
		},
		{
			name: 'PostgreSQL',
			logo: 'https://wiki.postgresql.org/images/a/a4/PostgreSQL_logo.3colors.svg',
			description: 'Banco de dados relacional'
		},
		{
			name: 'Railway',
			logo: 'https://railway.app/brand/logo-dark.svg',
			description: 'Plataforma de hospedagem na nuvem'
		}
	];

	const svelteFeatures = [
		{
			title: 'Simplicidade',
			description: 'Sintaxe intuitiva e menos boilerplate que React ou Vue'
		},
		{
			title: 'Performance',
			description: 'Compilador gera código otimizado automaticamente'
		},
		{
			title: 'Reatividade Verdadeira',
			description: 'Sistema de reatividade integrado sem necessidade de Hooks'
		},
		{
			title: 'Bundles Pequenos',
			description: 'Código compilado significativamente menor'
		}
	];

	const mvcArchitecture = [
		{
			name: 'Model',
			tech: 'Drizzle ORM + PostgreSQL',
			responsibilities: ['Schemas de dados', 'Validações', 'Queries ao banco', 'Lógica de dados'],
			color: '#4ecdc4'
		},
		{
			name: 'View',
			tech: 'Svelte Components + TailwindCSS',
			responsibilities: [
				'Componentes reativos',
				'Interface do usuário',
				'Estilização',
				'Interação com usuário'
			],
			color: '#ff6b6b'
		},
		{
			name: 'Controller',
			tech: 'SvelteKit remote functions',
			responsibilities: [
				'Ponte entre model e view',
				'Recebe e processa requisições',
				'Aplica regras de controle (autenticação, autorização, validação extra)'
			],
			color: '#ffd700'
		}
	];

	const diagrams = [
		{
			title: 'Diagrama de classes',
			url: '/classes.png'
		},
		{
			title: 'Diagrama de componentes',
			url: '/componentes.png'
		},
		{
			title: 'Diagrama lógico ER',
			url: '/diagramaER.png'
		}
	];
</script>

<Slide>
	<div class="title-slide">
		<div class="coin-logo">
			<img src="https://cdn-icons-png.flaticon.com/512/1175/1175277.png" alt="" />
		</div>
		<h1 class="main-title">BNP COIN</h1>
		<p class="subtitle">Sistema de Gamificação Educacional</p>
		<p class="tagline">Alunos: Breno, Nicolas Ferreira, Pedro Santos</p>
	</div>
</Slide>

<Slide>
	<div class="content-slide">
		<h2 class="slide-heading">Tecnologia</h2>
		<div class="tech-stack">
			<div class="tech-items">
				{#each technologies as item}
					<div class="tech-item">
						<img src={item.logo} alt={item.name} class="tech-logo" />
						<span class="tech-name">{item.name}</span>
					</div>
				{/each}
			</div>
		</div>
	</div>
</Slide>
<Slide>
	<Slide animate>
		<div class="content-slide">
			<div class="svelte-header">
				<img
					src="https://raw.githubusercontent.com/sveltejs/branding/master/svelte-logo.svg"
					alt="Svelte"
					class="svelte-logo-header"
				/>
				<h2 class="slide-heading">Sobre Svelte</h2>
			</div>
			<div class="feature-grid">
				{#each svelteFeatures as feature}
					<div class="feature-card">
						<h3>{feature.title}</h3>
						<p>{feature.description}</p>
					</div>
				{/each}
			</div>
			<div class="info-badge">
				<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
					<path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"></path>
				</svg>
				<span>Svelte compila para JavaScript vanilla</span>
			</div>
		</div>
	</Slide>
	<Slide>
		<div class="content-slide">
			<h2 class="slide-heading">Svelte vs React</h2>
			<div class="bundle-comparison">
				<div class="bundle-card svelte-card">
					<div class="framework-name">
						<img
							src="https://raw.githubusercontent.com/sveltejs/branding/master/svelte-logo.svg"
							alt="Svelte"
							class="comparison-logo"
						/>
						<h3>Svelte</h3>
					</div>
					<div class="bundle-size">
						<span class="size-number">1.6</span>
						<span class="size-unit">KB</span>
					</div>
					<p class="size-label">Bundle mínimo (gzip)</p>
					<ul class="comparison-features">
						<li>✓ Código compilado</li>
						<li>✓ Reatividade nativa</li>
						<li>✓ Parecido com simples JS</li>
						<li>✓ Menor curva de aprendizado</li>
					</ul>
				</div>

				<div class="bundle-card react-card">
					<div class="framework-name">
						<svg viewBox="0 0 24 24" fill="#61DAFB" class="comparison-logo">
							<circle cx="12" cy="12" r="2"></circle>
							<ellipse cx="12" cy="12" rx="10" ry="4" fill="none" stroke="#61DAFB" stroke-width="1"
							></ellipse>
							<ellipse
								cx="12"
								cy="12"
								rx="10"
								ry="4"
								fill="none"
								stroke="#61DAFB"
								stroke-width="1"
								transform="rotate(60 12 12)"
							></ellipse>
							<ellipse
								cx="12"
								cy="12"
								rx="10"
								ry="4"
								fill="none"
								stroke="#61DAFB"
								stroke-width="1"
								transform="rotate(120 12 12)"
							></ellipse>
						</svg>
						<h3>React + ReactDOM</h3>
					</div>
					<div class="bundle-size">
						<span class="size-number">34.8</span>
						<span class="size-unit">KB</span>
					</div>
					<p class="size-label">Bundle mínimo (gzip)</p>
					<ul class="comparison-features">
						<li>• Runtime necessário</li>
						<li>• Hooks para reatividade</li>
						<li>• Maior overhead</li>
						<li>• JSX como sintaxe</li>
					</ul>
				</div>
			</div>
		</div>
	</Slide>
</Slide>

<Slide>
	<Slide>
		<div class="content-slide">
			<h2 class="slide-heading">Arquitetura MVC</h2>
			<div class="mvc-diagram-split">
				{#each mvcArchitecture as layer}
					<div class="mvc-box" style="border-color: {layer.color}">
						<h3>{layer.name}</h3>
						<p>{layer.tech}</p>
						<ul class="mvc-list m-0 p-0">
							{#each layer.responsibilities as responsibility}
								<li>{responsibility}</li>
							{/each}
						</ul>
					</div>
				{/each}
			</div>
		</div>
	</Slide>

	<Slide>
		<div class="content-slide">
			<h2 class="slide-heading">Modelagem do Projeto</h2>
			<div class="diagrams-grid">
				{#each diagrams as diagram}
					<div class="diagram-card">
						<img src={diagram.url} alt={diagram.title} class="diagram-image" />
						<h3>{diagram.title}</h3>
					</div>
				{/each}
			</div>
		</div>
	</Slide>
	{#each diagrams.slice(0, 1) as diagram}
		<Slide>
			<div class="content-slide">
				<h2 class="slide-heading">{diagram.title}</h2>
				<img src={diagram.url} alt={diagram.title} />
			</div>
		</Slide>
	{/each}
	<Slide animate>
		<h2 class="slide-heading">Exemplo: Model</h2>
		<Code id="code-model" lines="1-8|10-14">
			{`
				export const professorT = pgTable('professor', {
					cpf: text('cpf').notNull(),
					id: serial('id').notNull().primaryKey(),
					departamento: text('departamento').notNull(),
					saldo: integer('saldo').default(1000).notNull(),
					userId: text('user_id')
						.references(() => user.id)
				});

				export const professorModel = {
					async listar() {
						return await db.select().from(professorT);
					}
				};
				`}
		</Code>
	</Slide>

	<Slide>
		<h2 class="slide-heading">Exemplo: Controller</h2>
		<Code id="code-controller" lines={'1-3'}>
			{`
				export const listarProfessores = query(async () => {
					return await professorModel.listar();
				});
				`}
		</Code>
	</Slide>

	<Slide animate>
		<h2 class="slide-heading">Exemplo: View</h2>
		<Code id="code-view" lines={'1-7|9-15'}>
			{`
				<script>
					let professores = $state([]);

					onMount(async () => {
						professores = await listarProfessores();
					});
				<script/>

				{#each professores as professor}
					<div>
						<h3>{professor.cpf}</h3>
						<p>Departamento: {professor.departamento}</p>
						<p>Saldo: {professor.saldo}</p>
					</div>
				{/each}
				`}
		</Code>
	</Slide>
</Slide>

<Slide>
	<div class="title-slide">
		<h1 class="main-title">Obrigado!</h1>
	</div>
</Slide>

<style>
	.title-slide {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100%;
		text-align: center;
	}

	.coin-logo {
		width: 80px;
		height: 80px;
		color: #ffd700;
		margin-bottom: 1.5rem;
		animation: rotate 4s linear infinite;
		filter: drop-shadow(0 0 30px rgba(255, 215, 0, 0.5));
	}

	.coin-logo svg {
		width: 100%;
		height: 100%;
	}

	@keyframes rotate {
		from {
			transform: rotateY(0deg);
		}
		to {
			transform: rotateY(360deg);
		}
	}

	.main-title {
		font-size: 5rem;
		font-weight: 900;
		background: linear-gradient(135deg, #ffd700, #ffed4e, #ffd700);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
		margin: 0;
		letter-spacing: 0.1em;
	}

	.subtitle {
		font-size: 1.5rem;
		color: #aaa;
		margin: 1rem 0;
		font-weight: 300;
	}

	.tagline {
		font-size: 1rem;
		color: #999;
		margin-top: 1.5rem;
		font-style: italic;
	}

	/* Description Box */
	.description-box {
		background: linear-gradient(135deg, rgba(255, 215, 0, 0.1), rgba(255, 165, 0, 0.1));
		border: 2px solid rgba(255, 215, 0, 0.3);
		border-radius: 16px;
		padding: 2rem;
		margin-bottom: 2rem;
	}

	.description-text {
		font-size: 1.5rem;
		line-height: 1.8;
		text-align: center;
		color: #ddd;
		margin: 0;
	}

	/* Content Slides */
	.content-slide {
		padding: 1rem;
		height: 100%;
		display: flex;
		flex-direction: column;
	}

	.slide-heading {
		font-size: 2.2rem;
		margin-bottom: 0.8rem;
		color: #ffd700;
		border-bottom: 3px solid #ffd700;
		padding-bottom: 0.8rem;
	}

	.svelte-header {
		display: flex;
		align-items: center;
		gap: 1.5rem;
	}

	.svelte-logo-header {
		width: 3.5rem;
		height: 3.5rem;
		object-fit: contain;
		animation: float 3s ease-in-out infinite;
	}

	@keyframes float {
		0%,
		100% {
			transform: translateY(0);
		}
		50% {
			transform: translateY(-10px);
		}
	}

	/* Feature Grid */
	.feature-grid {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 1.5rem;
	}

	.feature-card {
		background: rgba(255, 255, 255, 0.05);
		border: 2px solid rgba(255, 215, 0, 0.3);
		border-radius: 16px;
		padding: 1.5rem;
		text-align: center;
		transition: all 0.3s ease;
	}

	.feature-card:hover {
		transform: translateY(-5px);
		border-color: #ffd700;
		box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
	}

	.feature-icon {
		width: 3rem;
		height: 3rem;
		margin: 0 auto 0.8rem;
		color: #ffd700;
	}

	.feature-card h3 {
		font-size: 1.4rem;
		margin: 0.8rem 0;
		color: #ffd700;
	}

	.feature-card p {
		font-size: 1rem;
		color: #ccc;
	}

	/* Diagrams Grid */
	.diagrams-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 2rem;
		margin-top: 2rem;
	}

	.diagram-card {
		background: rgba(255, 255, 255, 0.05);
		border: 2px solid rgba(255, 215, 0, 0.3);
		border-radius: 16px;
		overflow: hidden;
		transition: all 0.3s ease;
		display: flex;
		flex-direction: column;
		padding: 0;
	}

	.diagram-card:hover {
		transform: translateY(-5px);
		border-color: #ffd700;
		box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
	}

	.diagram-image {
		width: 100%;
		min-width: 100%;
		max-width: 100%;
		height: 200px;
		object-fit: cover;
		padding: 0;
		margin: 0;
		background: rgba(0, 0, 0, 0.3);
		display: block;
		flex-shrink: 0;
	}

	.diagram-card h3 {
		font-size: 1.1rem;
		color: #ffd700;
		margin: 0.8rem 0.8rem 0.4rem 0.8rem;
	}

	/* Individual Diagram Slides */
	.content-slide > img {
		max-width: 90%;
		max-height: 70vh;
		object-fit: contain;
		margin: 2rem auto;
		border-radius: 12px;
		background: rgba(0, 0, 0, 0.3);
		padding: 1rem;
		border: 2px solid rgba(255, 215, 0, 0.3);
	}

	/* Tech Stack */
	.tech-stack {
		display: grid;
		gap: 3rem;
		margin-top: 2rem;
	}

	.tech-category {
		background: rgba(255, 255, 255, 0.05);
		border-radius: 20px;
		padding: 2rem;
		border: 2px solid rgba(255, 215, 0, 0.2);
	}

	.tech-category h3 {
		font-size: 2rem;
		color: #ffd700;
		margin-bottom: 1.5rem;
		text-align: center;
	}

	.tech-items {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	.tech-item {
		background: rgba(255, 255, 255, 0.08);
		padding-left: 1rem;
		border-radius: 12px;
		display: flex;
		align-items: center;
		gap: 1.5rem;
		transition: all 0.3s ease;
		border: 2px solid transparent;
	}

	.tech-item:hover {
		transform: translateX(10px);
		border-color: #ffd700;
	}

	.tech-logo {
		width: 2rem;
		height: 2rem;
		object-fit: contain;
	}

	.tech-logo-svg {
		width: 2rem;
		height: 2rem;
		color: #ffd700;
	}

	.tech-name {
		font-size: 1.2rem;
		font-weight: 600;
		color: #fff;
	}

	/* MVC Diagram */
	.mvc-diagram-split {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 2rem;
		margin-top: 2rem;
	}

	.mvc-diagram-single {
		display: flex;
		justify-content: center;
		margin-top: 2rem;
	}

	.mvc-diagram-single .mvc-box {
		max-width: 500px;
	}

	.mvc-box {
		background: rgba(255, 255, 255, 0.05);
		border-radius: 16px;
		padding: 1rem;
		text-align: center;
		transition: all 0.3s ease;
	}

	.mvc-box:hover {
		transform: scale(1.05);
	}

	.mvc-box.model {
		border: 3px solid #4ecdc4;
	}

	.mvc-box.view {
		border: 3px solid #ff6b6b;
	}

	.mvc-box.controller {
		border: 3px solid #ffd700;
	}

	.mvc-icon {
		width: 4rem;
		height: 4rem;
		margin: 0 auto 1rem;
		color: #ffd700;
	}

	.mvc-box h3 {
		font-size: 1.5rem;
		margin: 0.8rem 0;
		color: #ffd700;
	}

	.mvc-box p {
		font-size: 1rem;
		color: #aaa;
		margin-bottom: 0.8rem;
	}

	.mvc-list {
		list-style: none;
		padding: 0;
		text-align: left;
		margin: 0;
	}

	.mvc-list li {
		padding: 0.4rem;
		margin: 0.2rem 0;
		font-size: 0.95rem;
		color: #ccc;
	}

	.mvc-list li::before {
		content: '▹ ';
		color: #ffd700;
		font-weight: bold;
	}

	.mvc-note {
		margin-top: 2rem;
		padding: 1.5rem;
		background: rgba(255, 215, 0, 0.1);
		border-radius: 12px;
		display: flex;
		align-items: center;
		gap: 1rem;
		justify-content: center;
	}

	.mvc-note svg {
		width: 2rem;
		height: 2rem;
		color: #ffd700;
		flex-shrink: 0;
	}

	.mvc-note p {
		font-size: 1.3rem;
		color: #ddd;
		margin: 0;
	}

	/* Comparison Box */
	.comparison-box {
		display: grid;
		grid-template-columns: 1fr auto 1fr;
		gap: 2rem;
		align-items: center;
		margin-top: 2rem;
	}

	.comparison-item {
		background: rgba(255, 255, 255, 0.05);
		border-radius: 16px;
		padding: 2rem;
	}

	.comparison-item.traditional {
		border: 2px solid rgba(150, 150, 150, 0.5);
	}

	.comparison-item.svelte {
		border: 2px solid rgba(255, 215, 0, 0.5);
	}

	.comparison-item h3 {
		font-size: 1.8rem;
		margin-bottom: 1.5rem;
		color: #ffd700;
	}

	.vs-divider {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 80px;
		height: 80px;
		background: rgba(255, 215, 0, 0.1);
		border-radius: 50%;
	}

	.vs-divider svg {
		width: 2.5rem;
		height: 2.5rem;
		color: #ffd700;
	}

	.styled-list {
		list-style: none;
		padding: 0;
	}

	.styled-list li {
		padding: 0.8rem;
		margin: 0.5rem 0;
		font-size: 1.3rem;
		position: relative;
		padding-left: 2rem;
	}

	.styled-list li::before {
		content: '▹';
		position: absolute;
		left: 0;
		color: #ffd700;
		font-weight: bold;
		font-size: 1.5rem;
	}

	/* Info Badge */
	.info-badge {
		background: linear-gradient(135deg, #4ecdc4, #44a8a0);
		color: white;
		padding: 1rem;
		border-radius: 12px;
		text-align: center;
		font-size: 1.1rem;
		font-weight: 600;
		margin-top: 1.5rem;
		display: flex;
		align-items: center;
		gap: 0.8rem;
		justify-content: center;
	}

	.info-badge svg {
		width: 1.5rem;
		height: 1.5rem;
		flex-shrink: 0;
	}

	/* Architecture Flow */
	.architecture-flow {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-top: 3rem;
		padding: 2rem;
		background: rgba(255, 255, 255, 0.03);
		border-radius: 16px;
	}

	.flow-step {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
	}

	.step-number {
		width: 50px;
		height: 50px;
		background: linear-gradient(135deg, #ffd700, #ffed4e);
		color: #000;
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 1.5rem;
		font-weight: 900;
		margin-bottom: 1rem;
	}

	.step-content h4 {
		font-size: 1.3rem;
		color: #ffd700;
		margin-bottom: 0.5rem;
	}

	.flow-arrow {
		margin: 0 1rem;
	}

	.flow-arrow svg {
		width: 2rem;
		height: 2rem;
		color: #ffd700;
	}

	/* Split View */
	.split-view {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 2rem;
		margin-top: 2rem;
	}

	.split-panel {
		background: rgba(255, 255, 255, 0.05);
		border-radius: 12px;
		padding: 1.5rem;
		border: 2px solid rgba(255, 215, 0, 0.3);
	}

	.split-panel h3 {
		text-align: center;
		color: #ffd700;
		font-size: 1.8rem;
		margin-bottom: 1rem;
	}

	/* Takeaway Grid */
	.takeaway-grid {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 2rem;
		margin-top: 2rem;
	}

	.takeaway {
		background: rgba(255, 255, 255, 0.05);
		border-left: 4px solid #ffd700;
		border-radius: 8px;
		padding: 2rem;
		display: flex;
		gap: 1.5rem;
		align-items: center;
	}

	.takeaway-number {
		background: linear-gradient(135deg, #ffd700, #ffed4e);
		color: #000;
		width: 60px;
		height: 60px;
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 2rem;
		font-weight: 900;
		flex-shrink: 0;
	}

	.takeaway p {
		font-size: 1.3rem;
		margin: 0;
	}

	/* Pros/Cons */
	.pros-cons {
		margin-top: 2rem;
	}

	.pros {
		background: rgba(255, 255, 255, 0.05);
		border-radius: 16px;
		padding: 2rem;
		border: 2px solid rgba(78, 205, 196, 0.5);
	}

	.emoji-list {
		list-style: none;
		padding: 0;
	}

	.emoji-list li {
		font-size: 1.5rem;
		padding: 1rem;
		margin: 0.5rem 0;
		background: rgba(255, 255, 255, 0.03);
		border-radius: 8px;
		display: flex;
		align-items: center;
		gap: 1rem;
	}

	.inline-icon {
		width: 1.5rem;
		height: 1.5rem;
		color: #ffd700;
		flex-shrink: 0;
	}

	/* Final Slide */
	.final-slide {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100%;
		text-align: center;
	}

	.final-icon {
		width: 120px;
		height: 120px;
		color: #ffd700;
		margin-bottom: 2rem;
		animation: bounce 2s ease-in-out infinite;
	}

	.final-icon svg {
		width: 100%;
		height: 100%;
	}

	@keyframes bounce {
		0%,
		100% {
			transform: translateY(0);
		}
		50% {
			transform: translateY(-20px);
		}
	}

	.final-title {
		font-size: 6rem;
		background: linear-gradient(135deg, #ffd700, #ffed4e);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
		margin-bottom: 1rem;
		font-weight: 900;
		letter-spacing: 0.1em;
	}

	.final-text {
		font-size: 2rem;
		color: #ccc;
		margin-bottom: 2rem;
	}

	.tech-badges-final {
		display: flex;
		gap: 1rem;
		flex-wrap: wrap;
		justify-content: center;
		margin-bottom: 3rem;
	}

	.badge {
		background: linear-gradient(135deg, #ffd700, #ffed4e);
		color: #000;
		padding: 0.8rem 1.5rem;
		border-radius: 25px;
		font-weight: 700;
		font-size: 1.2rem;
	}

	.final-quote {
		font-size: 1.4rem;
		color: #999;
		font-style: italic;
		margin-top: 2rem;
		line-height: 1.8;
	}

	.team-credits {
		font-size: 1.5rem;
		color: #ffd700;
		margin-top: 2rem;
		font-weight: 600;
	}

	/* Demo Container */
	.demo-container {
		display: flex;
		align-items: center;
		justify-content: center;
		height: 70vh;
		margin-top: 2rem;
	}

	.demo-button {
		background: linear-gradient(135deg, #ffd700, #ffed4e);
		color: #000;
		border: none;
		padding: 2rem 3rem;
		border-radius: 20px;
		font-size: 2rem;
		font-weight: 700;
		cursor: pointer;
		display: flex;
		align-items: center;
		gap: 1.5rem;
		transition: all 0.3s ease;
		box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
	}

	.demo-button:hover {
		transform: translateY(-5px) scale(1.05);
		box-shadow: 0 15px 40px rgba(255, 215, 0, 0.5);
	}

	.demo-button svg {
		width: 3rem;
		height: 3rem;
	}

	.iframe-container {
		position: relative;
		width: 100%;
		height: 100%;
		border-radius: 12px;
		overflow: hidden;
		border: 3px solid #ffd700;
		box-shadow: 0 10px 40px rgba(255, 215, 0, 0.3);
	}

	.close-button {
		position: absolute;
		top: 1rem;
		right: 1rem;
		z-index: 10;
		background: rgba(255, 0, 0, 0.8);
		color: white;
		border: none;
		width: 40px;
		height: 40px;
		border-radius: 50%;
		cursor: pointer;
		display: flex;
		align-items: center;
		justify-content: center;
		transition: all 0.3s ease;
	}

	.close-button:hover {
		background: rgba(255, 0, 0, 1);
		transform: scale(1.1);
	}

	.close-button svg {
		width: 20px;
		height: 20px;
	}

	.demo-iframe {
		width: 100%;
		height: 100%;
		border: none;
		background: white;
	}

	/* Bundle Comparison */
	.bundle-comparison {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 2rem;
		margin-top: 1rem;
		margin-bottom: 1.5rem;
	}

	.bundle-card {
		background: rgba(255, 255, 255, 0.05);
		border-radius: 20px;
		padding: 1.2rem;
		text-align: center;
		transition: all 0.3s ease;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.svelte-card {
		border: 3px solid #ff3e00;
		box-shadow: 0 5px 20px rgba(255, 62, 0, 0.2);
	}

	.svelte-card:hover {
		transform: translateY(-10px);
		box-shadow: 0 15px 40px rgba(255, 62, 0, 0.4);
	}

	.react-card {
		border: 3px solid #61dafb;
		box-shadow: 0 5px 20px rgba(97, 218, 251, 0.2);
	}

	.react-card:hover {
		transform: translateY(-10px);
		box-shadow: 0 15px 40px rgba(97, 218, 251, 0.4);
	}

	.framework-name {
		display: flex;
		align-items: center;
		gap: 0.8rem;
		margin-bottom: 1.2rem;
	}

	.comparison-logo {
		width: 2.5rem;
		height: 2.5rem;
	}

	.framework-name h3 {
		font-size: 1.4rem;
		color: #ffd700;
		margin: 0;
	}

	.bundle-size {
		margin: 0;
	}

	.size-number {
		font-size: 3.5rem;
		font-weight: 900;
		background: linear-gradient(135deg, #ffd700, #ffed4e);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
	}

	.size-unit {
		font-size: 1.5rem;
		color: #aaa;
		margin-left: 0.3rem;
	}

	.size-label {
		font-size: 1rem;
		color: #999;
		margin-bottom: 1.2rem;
	}

	.comparison-features {
		list-style: none;
		padding: 0;
		text-align: left;
		width: 100%;
		margin: 0;
	}

	.comparison-features li {
		padding: 0.5rem 0.8rem;
		margin: 0.3rem 0;
		font-size: 1rem;
		color: #ddd;
		background: rgba(255, 255, 255, 0.03);
		border-radius: 8px;
	}

	.performance-metrics {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 1.5rem;
		margin-top: 2rem;
	}

	.metric-item {
		background: rgba(255, 215, 0, 0.08);
		border: 2px solid rgba(255, 215, 0, 0.3);
		border-radius: 16px;
		padding: 1.5rem;
		display: flex;
		gap: 1rem;
		align-items: flex-start;
		transition: all 0.3s ease;
	}

	.metric-item:hover {
		transform: translateY(-5px);
		border-color: #ffd700;
		background: rgba(255, 215, 0, 0.15);
	}

	.metric-icon {
		font-size: 2.5rem;
		flex-shrink: 0;
	}

	.metric-content h4 {
		font-size: 1.3rem;
		color: #ffd700;
		margin: 0 0 0.5rem 0;
	}

	.metric-content p {
		font-size: 1.1rem;
		color: #ccc;
		margin: 0;
		line-height: 1.5;
	}

	.metric-content strong {
		color: #ffd700;
		font-weight: 700;
	}
</style>
