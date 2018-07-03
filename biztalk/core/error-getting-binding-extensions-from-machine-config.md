---
title: Machine.config からバインド拡張機能を取得中にエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65ab48cf-575b-4db6-984a-880f7e286959
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c65c0341941634bb11bd058bfcbe9c365c612d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990731"
---
# <a name="error-getting-binding-extensions-from-machineconfig"></a><span data-ttu-id="6c2b7-102">machine.config からバインド拡張機能を取得中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="6c2b7-102">Error getting binding extensions from machine.config</span></span>
## <a name="details"></a><span data-ttu-id="6c2b7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6c2b7-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="6c2b7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6c2b7-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="6c2b7-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6c2b7-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="6c2b7-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6c2b7-106">Event ID</span></span>     |                                         <span data-ttu-id="6c2b7-107">0</span><span class="sxs-lookup"><span data-stu-id="6c2b7-107">0</span></span>                                          |
|  <span data-ttu-id="6c2b7-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6c2b7-108">Event Source</span></span>   |                                         <span data-ttu-id="6c2b7-109">0</span><span class="sxs-lookup"><span data-stu-id="6c2b7-109">0</span></span>                                          |
|    <span data-ttu-id="6c2b7-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6c2b7-110">Component</span></span>    |                                         <span data-ttu-id="6c2b7-111">0</span><span class="sxs-lookup"><span data-stu-id="6c2b7-111">0</span></span>                                          |
|  <span data-ttu-id="6c2b7-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6c2b7-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="6c2b7-113">0</span><span class="sxs-lookup"><span data-stu-id="6c2b7-113">0</span></span>                                          |
|  <span data-ttu-id="6c2b7-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6c2b7-114">Message Text</span></span>   |                <span data-ttu-id="6c2b7-115">machine.config からバインド拡張機能を取得中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="6c2b7-115">Error getting binding extensions from machine.config</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="6c2b7-116">説明</span><span class="sxs-lookup"><span data-stu-id="6c2b7-116">Explanation</span></span>  
 <span data-ttu-id="6c2b7-117">このエラーは、受信場所または送信ポートのバインディング構成にはユーザー定義のバインディング拡張機能がありますが、machine.config ファイルに定義されていないときに発生します。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-117">This error occurs when a  receive location or send port binding configuration has a user defined binding extension, but it is not defined in machine.config file.</span></span> <span data-ttu-id="6c2b7-118">この状況は、主に WCF-Custom アダプターおよび WCF-CustomIsolated アダプターで発生します。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6c2b7-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6c2b7-119">User Action</span></span>  
 <span data-ttu-id="6c2b7-120">受信場所または送信ポートに使用されているバインディング拡張機能を machine.config ファイルに定義します。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-120">Define the binding extension used in the receive location or send port in machine.config file.</span></span> <span data-ttu-id="6c2b7-121">また、カスタムの動作またはバインディング要素を WCF-Custom アダプターで使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-121">Also, to get a custom behavior or binding element to work with WCF-Custom adapter, complete these steps:</span></span>  
  
1.  <span data-ttu-id="6c2b7-122">アセンブリを GAC にします。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-122">GAC the assembly</span></span>  
  
2.  <span data-ttu-id="6c2b7-123">Machine.config ファイルを変更 (で見つかった **%FrameworkDir%\v4.0.30319\CONFIG**)。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-123">Modify your machine.config file (found in **%FrameworkDir%\v4.0.30319\CONFIG**).</span></span>  
  
    1.  <span data-ttu-id="6c2b7-124">動作のサービス構成エディター内で DLL を読み込む (**svcConfigEditor.exe**)。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-124">Load your behavior DLL inside the Service Configuration Editor (**svcConfigEditor.exe**).</span></span>  
  
    2.  <span data-ttu-id="6c2b7-125">構成を保存、 **app.config**ファイル</span><span class="sxs-lookup"><span data-stu-id="6c2b7-125">Save the configuration to an **app.config** file</span></span>  
  
    3.  <span data-ttu-id="6c2b7-126">コピーして貼り付け、 **system.servicemodel** machine.config の同様のセクションの extensions セクション。場合**system.servicemodel**セクションがあります、machine.config に存在しない 1 つを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-126">Copy and paste the **system.servicemodel** extensions section in a similar section in machine.config. If **system.servicemodel** section is not present in machine.config, your must create one.</span></span> <span data-ttu-id="6c2b7-127">次に、machine.config ファイルの構成セクションの例を示します。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-127">The following is an example from the configuration section of a machine.config file:</span></span>  
  
        ```  
          <system.serviceModel>  
            <extensions>  
              <behaviorExtensions>  
                <add name="BizTalkWcfContractNamespaceTestServiceBehaviorExtension" type="ASB.BizTalk.Samples.BizTalkWcfContractNamespaceTestServiceBehaviorExtension, CustomBizTalkWcfBehaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=7631521c07cf34b4" />  
              </behaviorExtensions>  
            </extensions>  
          </system.serviceModel>  
        ```  
  
> [!NOTE]
>  <span data-ttu-id="6c2b7-128">上記のコードは、WCF 拡張機能 タブにも追加できます。場合は、拡張機能は、受信側である必要がありますを参照してください、 **\<ホスト名\>プロパティ ダイアログ ボックスで、WCF 拡張機能**タブ (Wcf-custom または Wcf-customisolated アダプターの受信ハンドラー)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-128">The above code can also be added to the WCF Extensions tab. If the extension needs to be on the receive side, see the **\<Host Name\> Properties Dialog Box, WCF Extensions** tab (WCF-Custom or WCF-CustomIsolated Adapter Receive Handler) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="6c2b7-129">表示拡張機能は、送信側である必要があります、 **\<ホスト名\>プロパティ ダイアログ ボックスで、WCF 拡張機能** タブ (Wcf-custom アダプターの送信ハンドラー)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-129">If the extension needs to be on the send side, see **\<Host Name\> Properties Dialog Box, WCF Extensions** tab (WCF-Custom Adapter Send Handler) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 3. <span data-ttu-id="6c2b7-130">管理コンソールを閉じ、開き直します。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-130">Close and reopen your admin console.</span></span> <span data-ttu-id="6c2b7-131">WCF-Custom アダプターのカスタム動作を確認できるようになります。また、管理コンソールを開くと、ポートは有効なままです。</span><span class="sxs-lookup"><span data-stu-id="6c2b7-131">You should be able to see your custom behavior in the WCF-Custom adapter, and the port should stay enabled when you enable it.</span></span>