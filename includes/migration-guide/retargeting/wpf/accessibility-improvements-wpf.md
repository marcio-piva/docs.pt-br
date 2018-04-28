### <a name="accessibility-improvements-in-wpf"></a><span data-ttu-id="de18e-101">Melhorias de acessibilidade no WPF</span><span class="sxs-lookup"><span data-stu-id="de18e-101">Accessibility improvements in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="de18e-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="de18e-102">Details</span></span>|<span data-ttu-id="de18e-103"><strong>Melhorias de Alto Contraste</strong></span><span class="sxs-lookup"><span data-stu-id="de18e-103"><strong>High Contrast improvements</strong></span></span><ul><li><span data-ttu-id="de18e-104">Agora, o foco do controle <xref:System.Windows.Controls.Expander> é visível.</span><span class="sxs-lookup"><span data-stu-id="de18e-104">The focus for the <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="de18e-105">Em versões anteriores do .NET Framework, ele não era.</span><span class="sxs-lookup"><span data-stu-id="de18e-105">In previous versions of the .NET Framework, it was not.</span></span></li><li><span data-ttu-id="de18e-106">Agora, é mais fácil ver o texto nos controles <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton> quando eles estão selecionados do que nas versões anteriores do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de18e-106">The text in <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls when they are selected is now easier to see than in previous .NET Framework versions.</span></span></li><li><span data-ttu-id="de18e-107">A borda de um <xref:System.Windows.Controls.ComboBox> desabilitado agora é da mesma cor do texto desabilitado.</span><span class="sxs-lookup"><span data-stu-id="de18e-107">The border of a disabled <xref:System.Windows.Controls.ComboBox> is now the same color as the disabled text.</span></span> <span data-ttu-id="de18e-108">Em versões anteriores do .NET Framework, ela não era.</span><span class="sxs-lookup"><span data-stu-id="de18e-108">In previous versions of the .NET Framework, it was not.</span></span></li><li><span data-ttu-id="de18e-109">Botões desabilitados e com foco usam a cor de tema correta.</span><span class="sxs-lookup"><span data-stu-id="de18e-109">Disabled and focused buttons now use the correct theme color.</span></span> <span data-ttu-id="de18e-110">Em versões anteriores do .NET Framework, isso não acontecia.</span><span class="sxs-lookup"><span data-stu-id="de18e-110">In previous versions of the .NET Framework, they did not.</span></span></li><li><span data-ttu-id="de18e-111">O botão suspenso agora fica visível quando o estilo de um controle <xref:System.Windows.Controls.ComboBox> é definido como <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType>. Em versões anteriores do .NET Framework, isso não acontecia.</span><span class="sxs-lookup"><span data-stu-id="de18e-111">The dropdown button is now visible when a <xref:System.Windows.Controls.ComboBox> control's style is set to <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType>, In previous versions of the .NET Framework, it was not.</span></span></li><li><span data-ttu-id="de18e-112">A seta de indicação de classificação em um controle <xref:System.Windows.Controls.DataGrid> agora usa cores do tema.</span><span class="sxs-lookup"><span data-stu-id="de18e-112">The sort indicator arrow in a <xref:System.Windows.Controls.DataGrid> control now uses theme colors.</span></span> <span data-ttu-id="de18e-113">Em versões anteriores do .NET Framework, isso não acontecia.</span><span class="sxs-lookup"><span data-stu-id="de18e-113">In previous versions of the .NET Framework, it did not.</span></span></li><li><span data-ttu-id="de18e-114">O estilo do hiperlink padrão agora é alterado para a cor de tema correto ao passar o mouse.</span><span class="sxs-lookup"><span data-stu-id="de18e-114">The default hyperlink style now changes to the correct theme color on mouse over.</span></span> <span data-ttu-id="de18e-115">Em versões anteriores do .NET Framework, isso não acontecia.</span><span class="sxs-lookup"><span data-stu-id="de18e-115">In previous versions of the .NET Framework, it did not.</span></span></li><li><span data-ttu-id="de18e-116">O foco do teclado em botões de opção agora fica visível.</span><span class="sxs-lookup"><span data-stu-id="de18e-116">The Keyboard focus on radio buttons is now visible.</span></span> <span data-ttu-id="de18e-117">Em versões anteriores do .NET Framework, isso não acontecia.</span><span class="sxs-lookup"><span data-stu-id="de18e-117">In previous versions of the .NET Framework, it was not.</span></span></li><li><span data-ttu-id="de18e-118">A coluna da caixa de seleção do controle <xref:System.Windows.Controls.DataGrid> usa as cores esperadas para o feedback de foco do teclado.</span><span class="sxs-lookup"><span data-stu-id="de18e-118">The <xref:System.Windows.Controls.DataGrid> control's checkbox column now uses the expected colors for keyboard focus feedback.</span></span> <span data-ttu-id="de18e-119">Em versões anteriores do .NET Framework, isso não acontecia.</span><span class="sxs-lookup"><span data-stu-id="de18e-119">In previous versions of the .NET Framework, it did not.</span></span></li><li><span data-ttu-id="de18e-120">Os visuais de foco do teclado agora são visíveis em <xref:System.Windows.Controls.ComboBox> e <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="de18e-120">the Keyboard focus visuals are now visible on <xref:System.Windows.Controls.ComboBox> and <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="de18e-121">Em versões anteriores do .NET Framework, isso não acontecia.</span><span class="sxs-lookup"><span data-stu-id="de18e-121">In previous versions of the .NET Framework, it was not.</span></span></li></ul><span data-ttu-id="de18e-122"><strong>Melhorias de interação do leitor de tela</strong></span><span class="sxs-lookup"><span data-stu-id="de18e-122"><strong>Screen reader interaction improvements</strong></span></span><ul><li><span data-ttu-id="de18e-123">Agora, controles <xref:System.Windows.Controls.Expander> são anunciados corretamente como grupos (expandir/recolher) por leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="de18e-123"><xref:System.Windows.Controls.Expander> controls are now correctly announced as groups (expand/collapse) by screen readers.</span></span></li><li><span data-ttu-id="de18e-124">Agora, controles <xref:System.Windows.Controls.DataGridCell> são anunciados corretamente como uma célula de grade de dados (localizada) por leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="de18e-124"><xref:System.Windows.Controls.DataGridCell> controls are now correctly announced as data grid cell (localized) by screen readers.</span></span></li><li><span data-ttu-id="de18e-125">Leitores de tela agora anunciam o nome de um <xref:System.Windows.Controls.ComboBox> editável.</span><span class="sxs-lookup"><span data-stu-id="de18e-125">Screen readers will now announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span></li><li><span data-ttu-id="de18e-126">Controles <xref:System.Windows.Controls.PasswordBox> não são mais anunciados como &quot;Nenhum item no modo de exibição&quot; por leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="de18e-126"><xref:System.Windows.Controls.PasswordBox> controls are no longer announced as &quot;no item in view&quot; by screen readers.</span></span></li></ul><span data-ttu-id="de18e-127"><strong>Suporte para LiveRegion</strong>Leitores de tela como o Narrador ajudam as pessoas a conhecer o conteúdo de interface do usuário de um aplicativo, geralmente descrevendo algo na interface do usuário que está focalizado, porque esse provavelmente é o elemento de mais interesse do usuário.</span><span class="sxs-lookup"><span data-stu-id="de18e-127"><strong>LiveRegion support</strong>Screen readers such as Narrator help people know the UI contents of an application, usually by describing something about the UI that's currently focused, because that is probably the element of most interest to the user.</span></span> <span data-ttu-id="de18e-128">No entanto, se um elemento da interface do usuário for alterado em alguma parte da tela e não tiver o foco, o usuário poderá não ser informado e poderá perder informações importantes.</span><span class="sxs-lookup"><span data-stu-id="de18e-128">However, if a UI element changes somewhere in the screen and it does not have the focus, the user may not be informed and miss important information.</span></span> <span data-ttu-id="de18e-129">LiveRegions devem resolver esse problema.</span><span class="sxs-lookup"><span data-stu-id="de18e-129">LiveRegions are meant to solve this problem.</span></span> <span data-ttu-id="de18e-130">Um desenvolvedor pode usá-las para informar o leitor de tela ou qualquer outro cliente de [Automação de interface do usuário] [Visão Geral da Automação da Interface do Usuário](~/docs/framework/ui-automation/ui-automation-overview.md) de que foi feita uma alteração importante em um elemento da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="de18e-130">A developer can use them to inform the screen reader or any other [UI Automation][UI Automation Overview](~/docs/framework/ui-automation/ui-automation-overview.md) client that an important change has been made to a UI element.</span></span> <span data-ttu-id="de18e-131">Em seguida, o leitor de tela pode decidir como e quando informar o usuário dessa alteração.</span><span class="sxs-lookup"><span data-stu-id="de18e-131">The screen reader can then decide how and when to inform the user of this change.</span></span> <span data-ttu-id="de18e-132">A propriedade LiveSetting também permite que o leitor de tela saiba o quanto é importante informar o usuário sobre a alteração feita na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="de18e-132">The LiveSetting property also lets the screen reader know how important it is to inform the user of the change made to the UI.</span></span>|
|<span data-ttu-id="de18e-133">Sugestão</span><span class="sxs-lookup"><span data-stu-id="de18e-133">Suggestion</span></span>|<span data-ttu-id="de18e-134"><strong>Como aceitar ou recusar essas alterações</strong>Para se beneficiar dessas alterações, o aplicativo deverá ser executado no .NET Framework 4.7.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="de18e-134"><strong>How to opt in or out of these changes</strong>In order for the application to benefit from these changes, it must run on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="de18e-135">O aplicativo pode se beneficiar dessas alterações de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="de18e-135">The application can benefit from these changes in either of the following ways:</span></span><ul><li><span data-ttu-id="de18e-136">Ele é recompilado para ser destinado ao .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="de18e-136">It is recompiled to target the .NET Framework 4.7.1.</span></span> <span data-ttu-id="de18e-137">Essas alterações de acessibilidade são habilitadas por padrão em aplicativos do WPF destinados ao .NET Framework 4.7.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="de18e-137">These accessibility changes are enabled by default on WPF applications that target the .NET Framework 4.7.1 or later.</span></span></li><li><span data-ttu-id="de18e-138">Ele recusa os comportamentos de acessibilidade herdados adicionando a seguinte [Opção de AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) à seção <code>&lt;runtime&gt;</code> do arquivo app.config e configurando-a como false, como mostra o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="de18e-138">It opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the <code>&lt;runtime&gt;</code> section of the app config file and setting it to false, as the following example shows.</span></span></li></ul><pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="de18e-139">Aplicativos destinados ao .NET Framework 4.7.1 ou posterior que desejam preservar o comportamento de acessibilidade herdado pode aceitar o uso das funcionalidades de acessibilidade herdadas definindo explicitamente essa opção de AppContext como <code>true</code>. Para ter uma visão geral da automação da interface do usuário, consulte [Visão Geral da Automação do Usuário](~/docs/framework/ui-automation/ui-automation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="de18e-139">Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to <code>true</code>.For an overview of UI automation, see the [UI Automation Overview](~/docs/framework/ui-automation/ui-automation-overview.md).</span></span>|
|<span data-ttu-id="de18e-140">Escopo</span><span class="sxs-lookup"><span data-stu-id="de18e-140">Scope</span></span>|<span data-ttu-id="de18e-141">Principal</span><span class="sxs-lookup"><span data-stu-id="de18e-141">Major</span></span>|
|<span data-ttu-id="de18e-142">Versão</span><span class="sxs-lookup"><span data-stu-id="de18e-142">Version</span></span>|<span data-ttu-id="de18e-143">4.7.1</span><span class="sxs-lookup"><span data-stu-id="de18e-143">4.7.1</span></span>|
|<span data-ttu-id="de18e-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="de18e-144">Type</span></span>|<span data-ttu-id="de18e-145">Redirecionando</span><span class="sxs-lookup"><span data-stu-id="de18e-145">Retargeting</span></span>|
|<span data-ttu-id="de18e-146">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="de18e-146">Affected APIs</span></span>|<ul><li><xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.AutomationProperties.SetLiveSetting(System.Windows.DependencyObject,System.Windows.Automation.AutomationLiveSetting)?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.AutomationProperties.GetLiveSetting(System.Windows.DependencyObject)?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore?displayProperty=nameWithType></li></ul>|
