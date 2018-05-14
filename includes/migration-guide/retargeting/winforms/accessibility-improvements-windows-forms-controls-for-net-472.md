### <a name="accessibility-improvements-in-windows-forms-controls-for-net-472"></a>Melhorias de acessibilidade nos controles do Windows Forms para o .NET 4.7.2

|   |   |
|---|---|
|Detalhes|O Windows Forms Framework está melhorando sua maneira de trabalhar com tecnologias de acessibilidade para melhorar o suporte aos clientes do Windows Forms. Isso inclui as seguintes alterações:<ul><li>Alterações para melhorar a exibição durante o modo de Alto Contraste.</li><li>Alterações para melhorar a navegação pelo teclado nos controles DataGridView e MenuStrip.</li><li>Alterações na interação com o Narrator.</li></ul>|
|Sugestão|<strong>Como aceitar ou recusar essas alterações</strong>Para que o aplicativo se beneficie dessas alterações, ele precisará ser executado no .NET Framework 4.7.2 ou posterior. O aplicativo pode se beneficiar dessas alterações de uma das seguintes maneiras:<ul><li>Ser recompilado para ser direcionado ao .NET Framework 4.7.2. Essas alterações de acessibilidade são habilitadas por padrão nos aplicativos do Windows Forms direcionados ao .NET Framework 4.7.2 ou posterior.</li><li>Ser direcionado ao .NET Framework 4.7.1 ou a uma versão anterior e recusar os comportamentos de acessibilidade herdados, adicionando a seguinte [Opção AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) à seção <code>&lt;runtime&gt;</code> do arquivo de configuração de aplicativo e definindo-a como <code>false</code>, como mostra o exemplo a seguir.</li></ul><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Observe que para aceitar os recursos de acessibilidade adicionados no .NET Framework 4.7.2, você também precisa aceitar os recursos de acessibilidade do .NET Framework 4.7.1. Os aplicativos direcionados ao .NET Framework 4.7.2 ou posterior que desejam preservar o comportamento de acessibilidade herdado podem aceitar o uso das funcionalidades de acessibilidade herdadas definindo explicitamente essa opção AppContext como <code>true</code>.<strong>Uso de cores definidas pelo SO em temas de Alto Contraste</strong><ul><li>A seta suspensa do <xref:System.Windows.Forms.ToolStripDropDownButton> agora usa cores definidas pelo SO no tema de Alto Contraste.</li><li>Os controles <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> com <xref:System.Windows.Forms.ButtonBase.FlatStyle> definido como <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> ou <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>, agora usam cores definidas pelo SO no tema de Alto Contraste quando selecionado. Anteriormente, as cores de texto e de tela de fundo não eram contrastantes e eram difíceis de ler.</li><li>Os controles contidos em uma <xref:System.Windows.Forms.GroupBox> que tem sua propriedade <xref:System.Windows.Forms.Control.Enabled> definida como <code>false</code> agora usam cores definidas pelo SO no tema de Alto Contraste.</li><li>Os controles <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> e <xref:System.Windows.Forms.ToolStripDropDownButton> têm uma taxa maior de contraste de luminosidade no modo de Alto Contraste.</li><li>Por padrão, a <xref:System.Windows.Forms.DataGridViewLinkCell> usará as cores definidas pelo SO no modo de Alto Contraste para a propriedade <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor?displayProperty=nameWithType>.</li></ul>Observação: o Windows 10 mudou os valores de algumas cores do sistema de Alto Contraste. A estrutura do Windows Forms é baseada na estrutura do Win32. Para obter a melhor experiência, execute a versão mais recente do Windows e aceite as alterações mais recentes do sistema operacional adicionando um arquivo app.manifest a um aplicativo de teste e removendo a marca de comentário do seguinte código:<pre><code>&lt;!-- Windows 10 --&gt;&#13;&#10;&lt;supportedOS Id=&quot;{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}&quot; /&gt;&#13;&#10;</code></pre><strong>Melhor suporte ao Narrador</strong><ul><li>O Narrator agora apresenta o valor da propriedade <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> quando apresenta o texto de um <xref:System.Windows.Forms.ToolStripMenuItem>.</li><li>O Narrator agora indica quando um <xref:System.Windows.Forms.ToolStripMenuItem> tem sua propriedade <xref:System.Windows.Forms.Control.Enabled> definida como <code>false</code>.</li><li>O Narrator agora fornece comentários sobre o estado de uma caixa de seleção quando a propriedade <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> está definida como <code>true</code>.</li><li>A ordem de foco do modo de varredura do Narrator agora é consistente com a ordem visual dos controles na janela de diálogo de download do ClickOnce.</li></ul><strong>Melhoria no suporte à acessibilidade da DataGridView</strong><ul><li>As linhas em uma <xref:System.Windows.Forms.DataGridView> agora podem ser classificadas usando o teclado. Agora um usuário pode usar a tecla F3 para classificar pela coluna atual.</li><li>Quando o <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> for definido como <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, o cabeçalho da coluna mudará de cor para indicar a coluna atual à medida que o usuário pressionar Tab para percorrer as células na linha atual.</li><li>A propriedade <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Parent?displayProperty=nameWithType> agora retorna o controle pai correto.</li></ul><strong>Melhoria das indicações visuais</strong><ul><li>Os controles <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> com uma propriedade <xref:System.Windows.Forms.ButtonBase.Text> vazia agora exibirão um indicador de foco quando receberem o foco.</li></ul><strong>Melhoria no suporte à grade de propriedade</strong><ul><li>Os elementos filhos do controle <xref:System.Windows.Forms.PropertyGrid> agora retornam um <code>true</code> para a propriedade <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> somente quando um elemento PropertyGrid está habilitado.</li><li>Os elementos filhos do controle <xref:System.Windows.Forms.PropertyGrid> agora retornam um <code>false</code> para a propriedade <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> somente quando um elemento PropertyGrid pode ser alterado pelo usuário.</li></ul>Para obter uma visão geral de automação da interface do usuário, confira a [Visão geral de automação da interface do usuário](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).<strong>Melhoria na navegação pelo teclado</strong><ul><li>O <xref:System.Windows.Forms.ToolStripButton> agora permite o foco quando contido em um <xref:System.Windows.Forms.ToolStripPanel> que tem a propriedade <xref:System.Windows.Forms.ToolStripPanel.TabStop> definida como <code>true</code></li></ul>|
|Escopo|Principal|
|Versão|4.7.2|
|Tipo|Redirecionando|
