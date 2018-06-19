---
title: WCF LOB Adapter SDK での展開パッケージを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10022981-7944-45d6-a78a-4d680a79b010
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 734d79e92a4864090720434b9a1fb83387a0a850
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966560"
---
# <a name="create-a-deployment-package-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="12522-102">WCF LOB Adapter SDK の配置パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="12522-102">Create a deployment package with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="12522-103">開発サイクル中にビルド、デバッグ、および Visual Studio 内で、アダプターを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="12522-103">During the development cycle, you can build, debug, and run your adapter within Visual Studio.</span></span> <span data-ttu-id="12522-104">アダプター ソリューションの出力は、DLL アセンブリです。</span><span class="sxs-lookup"><span data-stu-id="12522-104">The output of an adapter solution is a DLL assembly.</span></span> <span data-ttu-id="12522-105">Visual Studio IDE を使用してアダプター ソリューションをビルドまたは devenv.exe スクリプトを使用して、アダプター アセンブリを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="12522-105">You can build your adapter solution using Visual Studio IDE or use the devenv.exe scripts to create an adapter assembly.</span></span> <span data-ttu-id="12522-106">アダプターを開発し、アダプターのコンシューマーの環境内で使用可能な状態である、アダプターはテスト環境や実稼働環境にインストールする展開パッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12522-106">Once the adapter is developed and it is ready for use within the adapter consumer's environment, you must create a deployment package that allows the adapter to be installed in test and production environments.</span></span>  
  
 <span data-ttu-id="12522-107">ソリューション内の Visual Studio のセットアップと配置プロジェクトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="12522-107">You can include a Visual Studio Setup and Deployment project within the solution.</span></span> <span data-ttu-id="12522-108">ソリューションのビルドの一部として、.msi ファイルを自動的に生成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="12522-108">This can be used to automatically generate an .msi file as part of the solution build.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12522-109">セットアップと配置プロジェクトは、ローカル ワークステーションに、Configuration Manager で ([ビルド] メニューに) Visual Studio .NET でを除外することで、ソリューションをビルドするたびに作成されないようにできます。</span><span class="sxs-lookup"><span data-stu-id="12522-109">You can prevent the Setup and Deployment project from building each time you build the solution on your local workstation by excluding it through the Configuration Manager (on the Build menu) within Visual Studio .NET.</span></span> <span data-ttu-id="12522-110">このメソッドを使用してソリューションのビルドからプロジェクトを除外する場合、ソース管理されたソリューション ファイルは影響しません。</span><span class="sxs-lookup"><span data-stu-id="12522-110">If you exclude a project from a solution build using this method, you do not affect the source controlled solution file.</span></span> <span data-ttu-id="12522-111">これは開発者特有であり、ソース管理下にないソリューション ユーザー オプション ファイル内では、変更が保持されます。</span><span class="sxs-lookup"><span data-stu-id="12522-111">Changes are maintained within the solution user option file, which is developer-specific and not under source control.</span></span>  
  
 <span data-ttu-id="12522-112">新しいプロジェクトがソリューションに追加されるたびに更新を新しいプロジェクトの出力が .msi ファイル内でインクルードされると、プロジェクト固有のインストール手順を実行することを確認するデプロイ プロジェクトを構成することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="12522-112">Whenever new projects are added to your solution you must remember to update and configure the deployment project to ensure that the output of the new project is included within the .msi file and that any project-specific installation steps are performed.</span></span>  
  
 <span data-ttu-id="12522-113">アダプター プロジェクトの出力をユーザーのコンピューターにインストールするには不十分です。</span><span class="sxs-lookup"><span data-stu-id="12522-113">It is not enough to just install the output of the adapter project on the user's computer.</span></span> <span data-ttu-id="12522-114">アダプターがグローバル アセンブリ キャッシュ (GAC) にインストールする必要があるし、が付いたアダプターを登録するように更新する必要があります、machine.config ファイル[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="12522-114">The adapter needs to be installed in global assembly cache (GAC) and the machine.config file needs to be updated to register the adapter with [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="12522-115">登録または登録解除のアダプターが使用できるサンプルのカスタム アクションを次に示します[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="12522-115">Following is a sample custom action that can be used to register or unregister an adapter with [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.ComponentModel;  
using System.Configuration.Install;  
  
using System.Reflection;  
using System.ServiceModel.Configuration;  
using System.Diagnostics;  
using System.Configuration;  
  
namespace Microsoft.Adapters.Samples.EchoV2  
{  
    //Custom action to register the adapter with WCF configuration in machine.config   
  
    //<system.serviceModel>  
    //  <extensions>  
    //    <bindingElementExtensions>  
    //      <add name="{BINDINGELEM_NAME}" type="{BINDINGELEM_TYPE}, {Assembly Information}" />  
    //    </bindingElementExtensions>  
    //    <bindingExtensions>  
    //      <add name="{BINDING_NAME}" type="{BINDING_TYPE}, {Assembly Information}" />  
    //    </bindingExtensions>  
    //  </extensions>  
    //  <client>  
    //    <endpoint binding="{BINDING_NAME}" contract="IMetadataExchange" name="{BINDING_SCHEME}" />  
    //  </client>  
    //</system.serviceModel>  
  
    [RunInstaller(true)]  
    public partial class WCFLOBAdapterInstaller : Installer  
    {  
        private Assembly adapterAssembly;  
        private Type bindingSectionType;  
        private Type bindingElementExtensionType;  
        const string INSTALLER_PARM_INSTALLDIR = "INSTALLDIR";  
        const string BINDING_ASSEMBLY_NAME = "Microsoft.Adapters.Samples.EchoV2.EchoAdapter.dll";  
        const string BINDINGELEM_NAME = "echoAdapterV2";  
        const string BINDINGELEM_TYPE = "Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement";  
        const string BINDING_NAME = "echoAdapterBindingV2";  
        const string BINDING_TYPE = "Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement";  
        const string BINDING_SCHEME = "echov2";  
  
        /// <summary>  
        /// Constructor - initialize the components and register the event handlers  
        /// </summary>  
        public WCFLOBAdapterInstaller()  
        {  
            InitializeComponent();  
            this.AfterInstall += new InstallEventHandler(AfterInstallEventHandler);  
            this.BeforeUninstall += new InstallEventHandler(BeforeUninstallEventHandler);  
        }  
  
        /// <summary>  
        /// Add the WCF configuration information in machine.config when installing the adapter.  
        /// </summary>  
        /// <param name="sender"></param>  
        /// <param name="e"></param>  
        private void AfterInstallEventHandler(object sender, InstallEventArgs e)  
        {  
            try  
            {  
                Debug.Assert(this.Context != null, "Context of this installation is null.");  
                string path = this.Context.Parameters[INSTALLER_PARM_INSTALLDIR] + BINDING_ASSEMBLY_NAME;  
                adapterAssembly = Assembly.LoadFrom(path);  
                Debug.Assert(adapterAssembly != null, "Adapter assembly is null.");  
                bindingSectionType = adapterAssembly.GetType(BINDING_TYPE, true);  
                Debug.Assert(bindingSectionType != null, "Binding type is null.");  
                bindingElementExtensionType = adapterAssembly.GetType(BINDINGELEM_TYPE, true);  
                Debug.Assert(bindingElementExtensionType != null, "Binding element extension type is null.");  
                AddMachineConfigurationInfo();  
            }  
            catch (Exception ex)  
            {  
                throw new InstallException("Error while adding adapter configuration information. " + ex.InnerException.Message);  
            }  
        }  
  
        /// <summary>  
        /// Registers the adapter with the WCF configuration  
        /// NOTE: The   
        /// </summary>  
        public void AddMachineConfigurationInfo()  
        {  
            System.Configuration.Configuration config = ConfigurationManager.OpenMachineConfiguration();  
            Debug.Assert(config != null, "Machine.Config returned null");  
            // add <client><endpoint>               
            ServiceModelSectionGroup sectionGroup = config.GetSectionGroup("system.serviceModel") as ServiceModelSectionGroup;  
            if (sectionGroup != null)  
            {  
  
                bool channelEndpointElementExists = false;  
                // this call can throw an exception if there is problem   
                // loading endpoint configurations - e.g. each endpoint  
                // tries to load binding which in turn loads the DLL  
                ClientSection clientSection = sectionGroup.Client;  
                foreach (ChannelEndpointElement elem in clientSection.Endpoints)  
                {  
                    if (elem.Binding.Equals(BINDING_NAME, StringComparison.OrdinalIgnoreCase) && elem.Name.Equals(BINDING_SCHEME, StringComparison.OrdinalIgnoreCase) && elem.Contract.Equals("IMetadataExchange", StringComparison.OrdinalIgnoreCase))  
                    {  
                        channelEndpointElementExists = true;  
                        break;  
                    }  
                }  
                if (!channelEndpointElementExists)  
                {  
                    Debug.WriteLine("Adding ChannelEndpointElement for : " + BINDING_NAME);  
                    ChannelEndpointElement elem = new ChannelEndpointElement();  
                    elem.Binding = BINDING_NAME;  
                    elem.Name = BINDING_SCHEME;  
                    elem.Contract = "IMetadataExchange";  
                    sectionGroup.Client.Endpoints.Add(elem);  
                    Debug.WriteLine("Added ChannelEndpointElement for : " + BINDING_NAME);  
                }  
  
                // add <bindingElementExtension>  
                if (!sectionGroup.Extensions.BindingElementExtensions.ContainsKey(BINDINGELEM_NAME))  
                {  
                    ExtensionElement ext = new ExtensionElement(BINDINGELEM_NAME, bindingElementExtensionType.FullName + "," + bindingElementExtensionType.Assembly.FullName);  
                    sectionGroup.Extensions.BindingElementExtensions.Add(ext);  
                }  
  
                // add <bindingExtension>  
                if (!sectionGroup.Extensions.BindingExtensions.ContainsKey(BINDING_NAME))  
                {  
                    ExtensionElement ext = new ExtensionElement(BINDING_NAME, bindingSectionType.FullName + "," + bindingSectionType.Assembly.FullName);  
                    sectionGroup.Extensions.BindingExtensions.Add(ext);  
                }  
  
                config.Save();  
            }  
            else throw new InstallException("Machine.Config doesn't contain system.serviceModel node");  
        }  
  
        /// <summary>  
        /// Remove the machine configuration information when uninstalling the adapter  
        /// </summary>  
        /// <param name="sender"></param>  
        /// <param name="e"></param>  
        private void BeforeUninstallEventHandler(object sender, InstallEventArgs e)  
        {  
            try  
            {  
                RemoveMachineConfigurationInfo();  
            }  
            catch (Exception ex)  
            {  
                throw new InstallException("Error while removing adapter configuration information" + ex.InnerException.Message);  
            }  
        }  
  
        /// <summary>  
        /// Unregisters the adapter with WCF configuration  
        /// </summary>  
        public void RemoveMachineConfigurationInfo()  
        {  
            System.Configuration.Configuration config = ConfigurationManager.OpenMachineConfiguration();  
            Debug.Assert(config != null, "Machine.Config returned null");  
            ServiceModelSectionGroup sectionGroup = config.GetSectionGroup("system.serviceModel") as ServiceModelSectionGroup;  
            ChannelEndpointElement elemToRemove = null;  
            if (sectionGroup != null)  
            {  
                // Remove <client><endpoint>  
                foreach (ChannelEndpointElement elem in sectionGroup.Client.Endpoints)  
                {  
                    if (elem.Binding.Equals(BINDING_NAME, StringComparison.OrdinalIgnoreCase) && elem.Name.Equals(BINDING_SCHEME, StringComparison.OrdinalIgnoreCase) && elem.Contract.Equals("IMetadataExchange", StringComparison.OrdinalIgnoreCase))  
                    {  
                        elemToRemove = elem;  
                        break;  
                    }  
                }  
                if (elemToRemove != null)  
                {  
                    Debug.WriteLine("Removing ChannelEndpointElement for : " + BINDING_NAME);  
                    sectionGroup.Client.Endpoints.Remove(elemToRemove);  
                    Debug.WriteLine("Removed ChannelEndpointElement for : " + BINDING_NAME);  
                }  
                // Remove <bindingExtension> for this adapter  
                if (sectionGroup.Extensions.BindingExtensions.ContainsKey(BINDING_NAME))  
                {  
                    sectionGroup.Extensions.BindingExtensions.RemoveAt(BINDING_NAME);  
                }  
                // Remove <bindingElementExtension> for this adapter  
                if (sectionGroup.Extensions.BindingElementExtensions.ContainsKey(BINDINGELEM_NAME))  
                {  
                    sectionGroup.Extensions.BindingElementExtensions.RemoveAt(BINDINGELEM_NAME);  
                }  
                config.Save();  
            }  
            else  
            {  
                throw new InstallException("Machine.Config doesn't contain system.serviceModel node");  
            }  
        }  
  
        /// <summary>  
        /// Use this for testing outside of the Setup project  
        /// </summary>  
        /// <param name="assemblyDirectory">Directory where the adapter assembly is located</param>  
        public static void TestAddConfiguration(string assemblyDirectory)  
        {  
            WCFLOBAdapterInstaller action = new WCFLOBAdapterInstaller();  
            InstallContext context = new InstallContext();  
            // In the Setup project, this is set by selecting custom action  
            // and in Properties setting /INSTALLDIR="[TARGETDIR]\" for CustomActionData  
            context.Parameters.Add("INSTALLDIR", assemblyDirectory);  
            action.Context = context;  
            action.AfterInstallEventHandler(null, null);  
        }  
  
        /// <summary>  
        /// Use this for testing outside of the Setup project  
        /// </summary>  
        /// <param name="assemblyDirectory">Directory where the adapter assembly is located</param>  
        public static void TestRemoveConfiguration(string assemblyDirectory)  
        {  
            WCFLOBAdapterInstaller action = new WCFLOBAdapterInstaller();  
            InstallContext context = new InstallContext();  
            // In the Setup project, this is set by selecting custom action  
            // and in Properties setting /INSTALLDIR="[TARGETDIR]\" for CustomActionData  
            context.Parameters.Add("INSTALLDIR", assemblyDirectory);  
            action.Context = context;  
            action.BeforeUninstallEventHandler(null, null);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="12522-116">展開パッケージにサンプル アダプターを調査する場合は、テストのコードとインストールのスクリプトを含む完成したエコー アダプターをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="12522-116">If you want to explore a sample adapter with a deployment package, you can download a completed Echo Adapter including test code and installation script.</span></span> <span data-ttu-id="12522-117">このサンプルは、BizTalk のインストール ファイルに含まれる`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`または`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`です。</span><span class="sxs-lookup"><span data-stu-id="12522-117">This sample is included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="12522-118">参照</span><span class="sxs-lookup"><span data-stu-id="12522-118">See Also</span></span>  
 <span data-ttu-id="12522-119">[WCF LOB アダプター SDK を使用して、アダプターを展開します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="12522-119">[Deploy an adapter using the WCF LOB adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md) </span></span>  
 [<span data-ttu-id="12522-120">WCF LOB アダプター SDK を使用してアダプターを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="12522-120">Undeploy an adapter using the WCF LOB adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/undeploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)