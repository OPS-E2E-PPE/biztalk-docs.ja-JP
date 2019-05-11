---
title: カスタム アダプターを展開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f17b336c-6232-4889-ab7e-92b83fab0f5f
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d04638aef5172eba3bae57a6f0d315fad66162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385300"
---
# <a name="how-to-deploy-a-custom-adapter"></a><span data-ttu-id="d9d85-102">カスタム アダプターを展開する方法</span><span class="sxs-lookup"><span data-stu-id="d9d85-102">How to Deploy a Custom Adapter</span></span>
<span data-ttu-id="d9d85-103">完全なアダプターのインストール プロセスは、次の手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="d9d85-103">A complete adapter installation process consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="d9d85-104">依存関係を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-104">Check dependencies.</span></span> <span data-ttu-id="d9d85-105">たとえば、MSMQ アダプターのインストーラーは、アダプター ランタイムに依存しているため、ローカル MSMQ サービスの存在をチェックします。</span><span class="sxs-lookup"><span data-stu-id="d9d85-105">For example, the MSMQ adapter installer checks for the existence of the local MSMQ service because the adapter runtime depends on it.</span></span>  
  
2.  <span data-ttu-id="d9d85-106">ローカル ファイル システムを設定します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-106">Set up the local file system.</span></span> <span data-ttu-id="d9d85-107">これには、インストール フォルダーを作成し、バイナリとサポート ファイルのコピーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d9d85-107">This includes creating installation folders and copying binary and support files.</span></span> <span data-ttu-id="d9d85-108">フォルダーへのアクセスおよびファイル アクセスのアクセス許可が正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-108">Ensure access to folders and file access permissions are configured properly.</span></span>  
  
3.  <span data-ttu-id="d9d85-109">システムのグローバル アセンブリ キャッシュには、マネージ アセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d9d85-109">Install managed assemblies into the system global assembly cache.</span></span>  
  
4.  <span data-ttu-id="d9d85-110">アダプターのレジストリ キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-110">Create registry keys for the adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d9d85-111">32 ビット アダプターの場合、BizTalk Server 管理コンソールは、レジストリの hkey_classes_root はカスタム アダプターの構成を取得するのに使用します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-111">For a 32-bit adapter, the BizTalk Server Administration Console uses the HKEY_CLASSES_ROOT branch in the registry to obtain custom adapter configuration.</span></span>  <span data-ttu-id="d9d85-112">32 ビット アダプターは、64 ビット サーバーにインストールする場合、BizTalk 機能の管理コンソール代わりに hkey_classes_root \wow6432node\ からアダプター構成データをします。</span><span class="sxs-lookup"><span data-stu-id="d9d85-112">If a 32-bit adapter is installed on a 64-bit server, the BizTalk Serve Administration Console instead uses the HKEY_CLASSES_ROOT\Wow6432Node\ branch for adapter configuration data.</span></span>  
  
5.  <span data-ttu-id="d9d85-113">BizTalk Server にアダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-113">Add the adapter to BizTalk Server.</span></span> <span data-ttu-id="d9d85-114">これは、プロパティの昇格を反映するために使用されるプロパティ スキーマの場合と同様のアダプターの BizTalk 管理データベースに新しいエントリを意味します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-114">This means new entries in the BizTalk Management database for the adapter as well as for the property schema used to reflect properties the adapter promotes.</span></span> <span data-ttu-id="d9d85-115">この手順では、BizTalk Server 管理コンソールを使用して手動で実行が場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9d85-115">This step is sometimes done manually using the BizTalk Server Administration console.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="d9d85-116">例外</span><span class="sxs-lookup"><span data-stu-id="d9d85-116">Exceptions</span></span>  
 <span data-ttu-id="d9d85-117">アダプターのインストーラーを部分的な BizTalk Server のインストールでの依存関係を確認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d9d85-117">The adapter installer may not need to check the dependencies in partial BizTalk Server installations.</span></span> <span data-ttu-id="d9d85-118">たとえば、管理ツールのみのインストール、アダプター インストーラー必要はありませんアダプター ランタイムが使用されていないために、アダプター ランタイムの依存関係を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-118">For example, in an administration tools-only installation, the adapter installer does not need to check adapter runtime dependencies because the adapter runtime is not used.</span></span> <span data-ttu-id="d9d85-119">方も BizTalk Server ランタイムのみのインストール場所、アダプターのインストーラーは、アダプター デザイン時の依存関係を確認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d9d85-119">The same is true in the BizTalk Server runtime-only installation, where the adapter installer does not need to check the adapter design-time dependencies.</span></span>  
  
 <span data-ttu-id="d9d85-120">複数の BizTalk Server 環境では、上記の一覧 (BizTalk Server にアダプターを追加する) の最後のステップは最初の BizTalk Server のアダプターのインストールでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-120">In multiple BizTalk Server environments, the last step in the preceding list (Add the adapter to BizTalk Server) only happens in the adapter installation on the first BizTalk Server.</span></span> <span data-ttu-id="d9d85-121">すべての BizTalk Server サービス インスタンス (既定名は、BizTalkMgmtDB) に同じ BizTalk 管理データベースを共有するためです。</span><span class="sxs-lookup"><span data-stu-id="d9d85-121">This is because all BizTalk Server service instances share the same BizTalk Management database (with the default name, BizTalkMgmtDB).</span></span> <span data-ttu-id="d9d85-122">同じグループ内の他の BizTalk server にアダプターを追加する場合は、追加の手順が失敗します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-122">If adapters are added to other BizTalk servers in the same group, the additional steps fail.</span></span>  
  
## <a name="install-the-adapter-assemblies-into-the-global-assembly-cache"></a><span data-ttu-id="d9d85-123">アダプター アセンブリをグローバル アセンブリ キャッシュにインストールします。</span><span class="sxs-lookup"><span data-stu-id="d9d85-123">Install the Adapter Assemblies into the Global Assembly Cache</span></span>  
 <span data-ttu-id="d9d85-124">別のアダプターのインストール パスで複数の BizTalk Server ホスト環境をサポートするには、システムのグローバル アセンブリ キャッシュにアダプターのアセンブリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d85-124">To support multiple BizTalk Server host environments with different adapter installation paths, the adapter assemblies must be installed into the system global assembly cache.</span></span>  
  
 <span data-ttu-id="d9d85-125">アダプターのインストールと構成は、新しいアダプターのエントリは、BizTalk 管理データベース (既定の名前 BizTalkMgmtDB) の adm_adapter テーブルに作成されます。</span><span class="sxs-lookup"><span data-stu-id="d9d85-125">During the adapter installation and configuration, a new adapter entry is created in the adm_adapter table of the BizTalk Management database (with the default name BizTalkMgmtDB).</span></span> <span data-ttu-id="d9d85-126">このエントリには、実行時とデザイン時の両方の BizTalk Server で使用されるすべての参照情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d9d85-126">This entry contains all reference information used by BizTalk Server for both run time and design time.</span></span>  
  
 <span data-ttu-id="d9d85-127">**InBoundAssemblyPath**と**OutboundAssemblyPath**フィールドは、アダプター バイナリの読み込み先を検索する、BizTalk Server ランタイムで使用します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-127">The **InBoundAssemblyPath** and **OutboundAssemblyPath** fields are used by the BizTalk Server runtime to find out where to load the adapter binaries.</span></span> <span data-ttu-id="d9d85-128">BizTalk Server グループの 1 つだけの BizTalk 管理データベースがあるため、グループ内のすべての BizTalk server はこの同じ特定の情報を共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d85-128">Because there is only one BizTalk Management database for a BizTalk Server group, all BizTalk servers in the group must share this same piece of information.</span></span> <span data-ttu-id="d9d85-129">グループ内の別の BizTalk server にアダプターをインストールする場合は、それらのサーバーで同じインストール パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d85-129">If you want to install the adapter on different BizTalk servers within the group, you must use the same installation path on each of those servers.</span></span> <span data-ttu-id="d9d85-130">ローカル インストール パスが BizTalk 管理データベースに格納されているパスと異なる場合は、BizTalk Server では、アダプター バイナリを読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="d9d85-130">If the local installation path is different from the path stored in the BizTalk Management database, BizTalk Server cannot load the adapter binaries.</span></span>  
  
 <span data-ttu-id="d9d85-131">常に、アダプターのアセンブリに厳密な名前で署名し、Gacutil.exe を使用して、アダプターのインストール中に、アダプター アセンブリをシステムのグローバル アセンブリ キャッシュに配置します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-131">Always sign the adapter's assembly with a strong name and use Gacutil.exe to put the adapter assembly into the system global assembly cache during the adapter installation.</span></span> <span data-ttu-id="d9d85-132">おくことを確認、 **InBoundAssemblyPath**と**OutboundAssemblyPath**フィールドを null または空です。</span><span class="sxs-lookup"><span data-stu-id="d9d85-132">Make sure that you leave the **InBoundAssemblyPath** and **OutboundAssemblyPath** fields null, or empty.</span></span>  
  
## <a name="using-the-framework-for-adapter-configuration"></a><span data-ttu-id="d9d85-133">アダプター構成のフレームワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-133">Using the Framework for Adapter Configuration</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d9d85-134">アダプター構成ユーザー インターフェイス (UI) プロパティ シートを生成するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-134">provides a mechanism for generating property sheets for the adapter configuration user interface (UI).</span></span> <span data-ttu-id="d9d85-135">構成のプロパティの XML スキーマ定義 (XSD) 定義に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d9d85-135">It is based on an XML Schema Definition (XSD) definition of the configuration properties.</span></span> <span data-ttu-id="d9d85-136">このフレームワークの使用は、アダプター開発者向けの大きな課題を紹介します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-136">The use of this framework introduces significant challenges for the adapter developer.</span></span> <span data-ttu-id="d9d85-137">このセクションでは、これらの問題の一部で、有効な回避策をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d9d85-137">This section suggests an effective workaround for some of these issues.</span></span>  
  
### <a name="consider-custom-property-editors-for-all-your-key-properties"></a><span data-ttu-id="d9d85-138">すべてのキーのプロパティのカスタム プロパティ エディターを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d9d85-138">Consider Custom Property Editors for all Your Key Properties</span></span>  
 <span data-ttu-id="d9d85-139">プロパティ シートにプロパティの上に重要なプロパティの検証を配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9d85-139">It is impossible to put significant property validation on top of properties in the property sheet.</span></span> <span data-ttu-id="d9d85-140">フレームワークは、UI の検証規則を定義する XML スキーマ定義 (XSD) の simpleType の制約を使用しようとします。</span><span class="sxs-lookup"><span data-stu-id="d9d85-140">The framework attempts to use XML Schema Definition (XSD) simpleType restrictions to define the validation rules for the UI.</span></span> <span data-ttu-id="d9d85-141">最大と最小値の単純なルールが適用されますが、正規表現の文字列フィールドの制限がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d9d85-141">The simple rules for maximum and minimum value are applied but the regular expression restriction for string fields is not supported.</span></span> <span data-ttu-id="d9d85-142">また、データは、制限が適用される前に、共通言語ランタイム (CLR) 型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d9d85-142">Also, the data is converted into common language runtime (CLR) types before the restriction is applied.</span></span> <span data-ttu-id="d9d85-143">つまり、UI のユーザーで範囲外のエラーではなく、暗号のような型変換エラーがされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9d85-143">This means the user of the UI sometimes gets a cryptic type-conversion error rather than an out-of-range error.</span></span> <span data-ttu-id="d9d85-144">すべての検証ロジックは不十分です。</span><span class="sxs-lookup"><span data-stu-id="d9d85-144">All in all, the validation logic is very weak.</span></span>  
  
 <span data-ttu-id="d9d85-145">多くのアダプター開発者が採用しているソリューションでは、そのプロパティ シートの主要なプロパティのカスタム プロパティ エディターを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-145">The solution many adapter developers have adopted is to write custom property editors for the main properties on their property sheet.</span></span> <span data-ttu-id="d9d85-146">場合 (大文字と小文字は多くの場合)、さまざまな相互依存プロパティがあるカスタム プロパティ エディターは、1 つのフィールドに結果を結合できます、ランタイムは後で区切ります。</span><span class="sxs-lookup"><span data-stu-id="d9d85-146">If there are a number of cross-dependent properties (as is often the case), then the custom property editor can combine the results into a single field and the runtime can later separate them.</span></span> <span data-ttu-id="d9d85-147">これは、インターフェイスに必要なは、(ただし、通常は少量) のカスタム コードを取得する唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="d9d85-147">This is the only way to get the necessary (though still generally trivial) custom code into the interface.</span></span>  
  
 <span data-ttu-id="d9d85-148">カスタム プロパティ エディターは比較的簡単に記述し、それらを使用する XSD のプロパティの注釈を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d9d85-148">Custom property editors are relatively straightforward to write and the property in the XSD can be annotated to use them.</span></span> <span data-ttu-id="d9d85-149">プロパティ エディターのエントリ ポイントを公開するアセンブリを参照して、注釈と CLR フォームを表示するにはコーディングしています。</span><span class="sxs-lookup"><span data-stu-id="d9d85-149">The annotation references an assembly that exposes the property editor entry point, and it is coded to show a CLR Form.</span></span> <span data-ttu-id="d9d85-150">通常のユーザー インターフェイスを記述し、Visual Studio によって提供される従来のインターフェイス生成ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9d85-150">You can now write a regular user interface and use the traditional interface-generation tools that Visual Studio offers.</span></span>  
  
 <span data-ttu-id="d9d85-151">次のコードでは、XSD を使用して、カスタム プロパティ エディターを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d9d85-151">The following code shows how to use the XSD to add a custom property editor:</span></span>  
  
```  
<xs:element name="queueDetails" type="xs:string" minOccurs="0">  
    <xs:annotation>  
        <xs:appinfo>  
           <baf:designer>  
               <baf:displayname _locID="queueName">Queue Definition</baf:displayname>  
               <baf:description _locID="receiveQueueDesc">Details of MQSeries Server, Queue Manager and Queue from where you want to receive messages.</baf:description>  
               <baf:category _locID="mqsCategory">MQSeries</baf:category>  
               <baf:editor assembly="Microsoft.BizTalk Server.Adapter.MQSAdmin.dll">Microsoft.BizTalk Server.Adapter.MQSAdmin.MQSUITypeEditor</baf:editor>  
            </baf:designer>  
        </xs:appinfo>  
    </xs:annotation>  
</xs:element>  
  
```  
  
 <span data-ttu-id="d9d85-152">参照されているコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d9d85-152">The code that is referenced should look like this:</span></span>  
  
```  
public class MQSUITypeEditor : System.Drawing.Design.UITypeEditor  
{  
public override System.Drawing.Design.UITypeEditorEditStyle GetEditStyle  
(System.ComponentModel.ITypeDescriptorContext context)   
{  
return System.Drawing.Design.UITypeEditorEditStyle.Modal;  
}  
public override object EditValue (System.ComponentModel.ITypeDescriptorContext context,  
System.IServiceProvider provider, object value)   
{  
Form qdForm = new QueueDefinitionForm(value);  
IWindowsFormsEditorService service =   
(IWindowsFormsEditorService)provider.GetService(typeof(IWindowsFormsEditorService));  
DialogResult dialogResult = service.ShowDialog(qdForm);  
//…  
}  
}  
class QueueDefinitionForm : System.Windows.Forms.Form   
{  
//  traditional UI code goes here!  
}  
  
```  
  
 <span data-ttu-id="d9d85-153">管理ランタイムでは、グローバル アセンブリ キャッシュに追加する必要がありますので、XSD で参照されるアセンブリを検索できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d85-153">The administration runtime must be able to find the assembly referenced in the XSD, so you should add it to the global assembly cache.</span></span>