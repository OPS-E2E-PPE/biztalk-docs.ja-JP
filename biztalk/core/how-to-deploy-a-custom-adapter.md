---
title: カスタム アダプターを展開する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: e36443b99f01688a38e66a4a302ab64bb220092f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250298"
---
# <a name="how-to-deploy-a-custom-adapter"></a><span data-ttu-id="c5872-102">カスタム アダプターを展開する方法</span><span class="sxs-lookup"><span data-stu-id="c5872-102">How to Deploy a Custom Adapter</span></span>
<span data-ttu-id="c5872-103">アダプターのインストールは、次の手順で行われます。</span><span class="sxs-lookup"><span data-stu-id="c5872-103">A complete adapter installation process consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="c5872-104">依存関係をチェックする。</span><span class="sxs-lookup"><span data-stu-id="c5872-104">Check dependencies.</span></span> <span data-ttu-id="c5872-105">たとえば、MSMQ アダプター ランタイムはローカル MSMQ サービスに依存するため、MSMQ アダプターのインストーラーはローカル MSMQ サービスが存在するかどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="c5872-105">For example, the MSMQ adapter installer checks for the existence of the local MSMQ service because the adapter runtime depends on it.</span></span>  
  
2.  <span data-ttu-id="c5872-106">ローカル ファイル システムを設定する。</span><span class="sxs-lookup"><span data-stu-id="c5872-106">Set up the local file system.</span></span> <span data-ttu-id="c5872-107">この設定作業には、インストール フォルダーの作成と、バイナリ ファイルおよびサポート ファイルのコピーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c5872-107">This includes creating installation folders and copying binary and support files.</span></span> <span data-ttu-id="c5872-108">フォルダーにアクセス可能で、ファイル アクセス許可が適切に構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c5872-108">Ensure access to folders and file access permissions are configured properly.</span></span>  
  
3.  <span data-ttu-id="c5872-109">マネージ アセンブリをシステムのグローバル アセンブリ キャッシュにインストールする。</span><span class="sxs-lookup"><span data-stu-id="c5872-109">Install managed assemblies into the system global assembly cache.</span></span>  
  
4.  <span data-ttu-id="c5872-110">アダプターのレジストリ キーを作成する。</span><span class="sxs-lookup"><span data-stu-id="c5872-110">Create registry keys for the adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c5872-111">32 ビット アダプターの場合、BizTalk Server 管理コンソールではレジストリ内の HKEY_CLASSES_ROOT からカスタム アダプター構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="c5872-111">For a 32-bit adapter, the BizTalk Server Administration Console uses the HKEY_CLASSES_ROOT branch in the registry to obtain custom adapter configuration.</span></span>  <span data-ttu-id="c5872-112">32 ビット アダプターが 64 ビット サーバーにインストールされている場合、BizTalk Server 管理コンソールでは、代わりに HKEY_CLASSES_ROOT\Wow6432Node\ からアダプター構成データを取得します。</span><span class="sxs-lookup"><span data-stu-id="c5872-112">If a 32-bit adapter is installed on a 64-bit server, the BizTalk Serve Administration Console instead uses the HKEY_CLASSES_ROOT\Wow6432Node\ branch for adapter configuration data.</span></span>  
  
5.  <span data-ttu-id="c5872-113">アダプターを BizTalk Server に追加する。</span><span class="sxs-lookup"><span data-stu-id="c5872-113">Add the adapter to BizTalk Server.</span></span> <span data-ttu-id="c5872-114">BizTalk 管理データベースにアダプターのエントリとプロパティ スキーマのエントリを新しく追加します。プロパティ スキーマは、アダプターによって昇格されるプロパティを反映するため使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5872-114">This means new entries in the BizTalk Management database for the adapter as well as for the property schema used to reflect properties the adapter promotes.</span></span> <span data-ttu-id="c5872-115">この手順は、BizTalk Server 管理コンソールを使用して手動で行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c5872-115">This step is sometimes done manually using the BizTalk Server Administration console.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="c5872-116">例外</span><span class="sxs-lookup"><span data-stu-id="c5872-116">Exceptions</span></span>  
 <span data-ttu-id="c5872-117">BizTalk Server の部分インストールでは、アダプター インストーラーで依存関係のチェックを行う必要がない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c5872-117">The adapter installer may not need to check the dependencies in partial BizTalk Server installations.</span></span> <span data-ttu-id="c5872-118">たとえば管理ツールのみのインストールの場合、アダプター ランタイムは必要ないため、アダプター インストーラーでアダプター ランタイムの依存関係をチェックする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c5872-118">For example, in an administration tools-only installation, the adapter installer does not need to check adapter runtime dependencies because the adapter runtime is not used.</span></span> <span data-ttu-id="c5872-119">BizTalk Server ランタイムのみのインストールの場合も同様に、アダプター インストーラーでアダプター デザイン時の依存関係をチェックする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c5872-119">The same is true in the BizTalk Server runtime-only installation, where the adapter installer does not need to check the adapter design-time dependencies.</span></span>  
  
 <span data-ttu-id="c5872-120">BizTalk Server が複数存在する環境の場合、上に示した最後の手順 (アダプターを BizTalk Server に追加する) は、最初の BizTalk Server にアダプターをインストールするときだけ実行します。</span><span class="sxs-lookup"><span data-stu-id="c5872-120">In multiple BizTalk Server environments, the last step in the preceding list (Add the adapter to BizTalk Server) only happens in the adapter installation on the first BizTalk Server.</span></span> <span data-ttu-id="c5872-121">この理由は、すべての BizTalk Server サービス インスタンスで同じ BizTalk 管理データベース (既定の名前は BizTalkMgmtDB) が共有されるためです。</span><span class="sxs-lookup"><span data-stu-id="c5872-121">This is because all BizTalk Server service instances share the same BizTalk Management database (with the default name, BizTalkMgmtDB).</span></span> <span data-ttu-id="c5872-122">同じグループ内の他の BizTalk Server にアダプターを追加しようとすると、手順は失敗します。</span><span class="sxs-lookup"><span data-stu-id="c5872-122">If adapters are added to other BizTalk servers in the same group, the additional steps fail.</span></span>  
  
## <a name="install-the-adapter-assemblies-into-the-global-assembly-cache"></a><span data-ttu-id="c5872-123">アダプター アセンブリをグローバル アセンブリ キャッシュにインストールする</span><span class="sxs-lookup"><span data-stu-id="c5872-123">Install the Adapter Assemblies into the Global Assembly Cache</span></span>  
 <span data-ttu-id="c5872-124">アダプターのインストール パスが異なる複数の BizTalk Server ホストが存在する環境をサポートするには、アダプター アセンブリをシステムのグローバル アセンブリ キャッシュにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5872-124">To support multiple BizTalk Server host environments with different adapter installation paths, the adapter assemblies must be installed into the system global assembly cache.</span></span>  
  
 <span data-ttu-id="c5872-125">アダプターのインストールと構成の過程では、BizTalk 管理データベース (既定の名前は BizTalkMgmtDB) の adm_adapter テーブルにアダプターのエントリが新しく作成されます。</span><span class="sxs-lookup"><span data-stu-id="c5872-125">During the adapter installation and configuration, a new adapter entry is created in the adm_adapter table of the BizTalk Management database (with the default name BizTalkMgmtDB).</span></span> <span data-ttu-id="c5872-126">このエントリには、BizTalk Server が実行時およびデザイン時の両方で使用するすべての参照情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c5872-126">This entry contains all reference information used by BizTalk Server for both run time and design time.</span></span>  
  
 <span data-ttu-id="c5872-127">**InBoundAssemblyPath**と**OutboundAssemblyPath**をアダプターのバイナリの読み込み先を調べるには、BizTalk Server ランタイムによりフィールドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5872-127">The **InBoundAssemblyPath** and **OutboundAssemblyPath** fields are used by the BizTalk Server runtime to find out where to load the adapter binaries.</span></span> <span data-ttu-id="c5872-128">BizTalk Server グループ用の BizTalk 管理データベースは 1 つだけなので、グループ内のすべての BizTalk Server で同じデータベースの情報を共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5872-128">Because there is only one BizTalk Management database for a BizTalk Server group, all BizTalk servers in the group must share this same piece of information.</span></span> <span data-ttu-id="c5872-129">グループ内の異なる BizTalk Server にアダプターをインストールする場合は、各サーバーで同じインストール パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5872-129">If you want to install the adapter on different BizTalk servers within the group, you must use the same installation path on each of those servers.</span></span> <span data-ttu-id="c5872-130">ローカルのインストール パスが BizTalk 管理データベースに格納されているパスと異なる場合、BizTalk Server ではアダプターのバイナリを読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="c5872-130">If the local installation path is different from the path stored in the BizTalk Management database, BizTalk Server cannot load the adapter binaries.</span></span>  
  
 <span data-ttu-id="c5872-131">常に、アダプターのアセンブリに厳密な名前で署名し、Gacutil.exe を使用して、アダプターのインストール中に、アダプター アセンブリをシステムのグローバル アセンブリ キャッシュに格納します。</span><span class="sxs-lookup"><span data-stu-id="c5872-131">Always sign the adapter's assembly with a strong name and use Gacutil.exe to put the adapter assembly into the system global assembly cache during the adapter installation.</span></span> <span data-ttu-id="c5872-132">ままにしておくことを確認してください、 **InBoundAssemblyPath**と**OutboundAssemblyPath**フィールドを null または空です。</span><span class="sxs-lookup"><span data-stu-id="c5872-132">Make sure that you leave the **InBoundAssemblyPath** and **OutboundAssemblyPath** fields null, or empty.</span></span>  
  
## <a name="using-the-framework-for-adapter-configuration"></a><span data-ttu-id="c5872-133">アダプター構成のフレームワークを使用する</span><span class="sxs-lookup"><span data-stu-id="c5872-133">Using the Framework for Adapter Configuration</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c5872-134"> では、アダプター構成ユーザー インターフェイス (UI) のプロパティ シートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="c5872-134"> provides a mechanism for generating property sheets for the adapter configuration user interface (UI).</span></span> <span data-ttu-id="c5872-135">このプロパティ シートは、構成プロパティの XML スキーマ定義 (XSD) が基になります。</span><span class="sxs-lookup"><span data-stu-id="c5872-135">It is based on an XML Schema Definition (XSD) definition of the configuration properties.</span></span> <span data-ttu-id="c5872-136">このフレームワークを使用する場合、アダプター開発者は多くの難問に直面します。</span><span class="sxs-lookup"><span data-stu-id="c5872-136">The use of this framework introduces significant challenges for the adapter developer.</span></span> <span data-ttu-id="c5872-137">ここでは、これらの難問を効果的に回避する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5872-137">This section suggests an effective workaround for some of these issues.</span></span>  
  
### <a name="consider-custom-property-editors-for-all-your-key-properties"></a><span data-ttu-id="c5872-138">すべての主要プロパティに対し、カスタム プロパティ エディターを使用する</span><span class="sxs-lookup"><span data-stu-id="c5872-138">Consider Custom Property Editors for all Your Key Properties</span></span>  
 <span data-ttu-id="c5872-139">プロパティ シートの上位のプロパティに対し、有意義なプロパティ検証を行うことは不可能です。</span><span class="sxs-lookup"><span data-stu-id="c5872-139">It is impossible to put significant property validation on top of properties in the property sheet.</span></span> <span data-ttu-id="c5872-140">このフレームワークは、XML スキーマ定義 (XSD) の SimpleType の制約を使用して UI の検証規則を定義しようとします。</span><span class="sxs-lookup"><span data-stu-id="c5872-140">The framework attempts to use XML Schema Definition (XSD) simpleType restrictions to define the validation rules for the UI.</span></span> <span data-ttu-id="c5872-141">このとき、最大値と最小値による単純な規則は適用されますが、文字列フィールドに対する正規表現の制約はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c5872-141">The simple rules for maximum and minimum value are applied but the regular expression restriction for string fields is not supported.</span></span> <span data-ttu-id="c5872-142">さらに、制約が適用される前に、データは共通言語ランタイム (CLR) 型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="c5872-142">Also, the data is converted into common language runtime (CLR) types before the restriction is applied.</span></span> <span data-ttu-id="c5872-143">これによって、UI のユーザーには範囲外のエラーではなく不明な型変換エラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c5872-143">This means the user of the UI sometimes gets a cryptic type-conversion error rather than an out-of-range error.</span></span> <span data-ttu-id="c5872-144">全体的に見て、この検証ロジックは不十分です。</span><span class="sxs-lookup"><span data-stu-id="c5872-144">All in all, the validation logic is very weak.</span></span>  
  
 <span data-ttu-id="c5872-145">多くのアダプター開発者が採用している解決策は、プロパティ シートの主要なプロパティに対し、カスタム プロパティ エディターを記述するというものです。</span><span class="sxs-lookup"><span data-stu-id="c5872-145">The solution many adapter developers have adopted is to write custom property editors for the main properties on their property sheet.</span></span> <span data-ttu-id="c5872-146">よくあるケースとして、相互に依存するプロパティが多くある場合は、カスタム プロパティ エディターを使用することで結果を単一のフィールドに結合できます。このフィールドは、ランタイムによって後で分離できます。</span><span class="sxs-lookup"><span data-stu-id="c5872-146">If there are a number of cross-dependent properties (as is often the case), then the custom property editor can combine the results into a single field and the runtime can later separate them.</span></span> <span data-ttu-id="c5872-147">必要な (通常は少量の) カスタム コードをインターフェイスに挿入するには、これが唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="c5872-147">This is the only way to get the necessary (though still generally trivial) custom code into the interface.</span></span>  
  
 <span data-ttu-id="c5872-148">カスタム プロパティ エディターの記述は比較的簡単です。XSD のプロパティには、カスタム プロパティ エディターを使用することを注釈で示すことができます。</span><span class="sxs-lookup"><span data-stu-id="c5872-148">Custom property editors are relatively straightforward to write and the property in the XSD can be annotated to use them.</span></span> <span data-ttu-id="c5872-149">この注釈では、プロパティ エディターのエントリ ポイントを公開するアセンブリへの参照を指定します。この注釈は、CLR フォームを表示するようコード化されます。</span><span class="sxs-lookup"><span data-stu-id="c5872-149">The annotation references an assembly that exposes the property editor entry point, and it is coded to show a CLR Form.</span></span> <span data-ttu-id="c5872-150">これで、標準的なユーザー インターフェイスを記述でき、Visual Studio で提供される従来のインターフェイス生成ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5872-150">You can now write a regular user interface and use the traditional interface-generation tools that Visual Studio offers.</span></span>  
  
 <span data-ttu-id="c5872-151">次のコードは、XSD を使用してカスタム プロパティ エディターを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c5872-151">The following code shows how to use the XSD to add a custom property editor:</span></span>  
  
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
  
 <span data-ttu-id="c5872-152">参照されるコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c5872-152">The code that is referenced should look like this:</span></span>  
  
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
  
 <span data-ttu-id="c5872-153">管理ランタイムでは XSD で参照されているアセンブリを特定できる必要があります。このため、アセンブリをグローバル アセンブリ キャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="c5872-153">The administration runtime must be able to find the assembly referenced in the XSD, so you should add it to the global assembly cache.</span></span>