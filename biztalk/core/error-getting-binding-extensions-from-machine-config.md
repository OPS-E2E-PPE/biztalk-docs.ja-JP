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
ms.openlocfilehash: 0ba98838d56287453b8d0b162dc531dbc3c1cbc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388823"
---
# <a name="error-getting-binding-extensions-from-machineconfig"></a><span data-ttu-id="67838-102">machine.config からバインド拡張機能を取得中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="67838-102">Error getting binding extensions from machine.config</span></span>
## <a name="details"></a><span data-ttu-id="67838-103">詳細</span><span class="sxs-lookup"><span data-stu-id="67838-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="67838-104">製品名</span><span class="sxs-lookup"><span data-stu-id="67838-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="67838-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="67838-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="67838-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="67838-106">Event ID</span></span>     |                                         <span data-ttu-id="67838-107">0</span><span class="sxs-lookup"><span data-stu-id="67838-107">0</span></span>                                          |
|  <span data-ttu-id="67838-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="67838-108">Event Source</span></span>   |                                         <span data-ttu-id="67838-109">0</span><span class="sxs-lookup"><span data-stu-id="67838-109">0</span></span>                                          |
|    <span data-ttu-id="67838-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="67838-110">Component</span></span>    |                                         <span data-ttu-id="67838-111">0</span><span class="sxs-lookup"><span data-stu-id="67838-111">0</span></span>                                          |
|  <span data-ttu-id="67838-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="67838-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="67838-113">0</span><span class="sxs-lookup"><span data-stu-id="67838-113">0</span></span>                                          |
|  <span data-ttu-id="67838-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="67838-114">Message Text</span></span>   |                <span data-ttu-id="67838-115">machine.config からバインド拡張機能を取得中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="67838-115">Error getting binding extensions from machine.config</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="67838-116">説明</span><span class="sxs-lookup"><span data-stu-id="67838-116">Explanation</span></span>  
 <span data-ttu-id="67838-117">受信場所のときに、このエラーが発生しますが、送信ポートのバインドの構成では、ユーザー定義のバインディング拡張機能または machine.config ファイルで定義されていません。</span><span class="sxs-lookup"><span data-stu-id="67838-117">This error occurs when a  receive location or send port binding configuration has a user defined binding extension, but it is not defined in machine.config file.</span></span> <span data-ttu-id="67838-118">Wcf-custom および Wcf-customisolated アダプターで主に、このような状況が発生します。</span><span class="sxs-lookup"><span data-stu-id="67838-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67838-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="67838-119">User Action</span></span>  
 <span data-ttu-id="67838-120">Machine.config ファイルでの送信ポートまたは受信場所で使用されるバインド拡張機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="67838-120">Define the binding extension used in the receive location or send port in machine.config file.</span></span> <span data-ttu-id="67838-121">また、カスタムの動作または WCF カスタム アダプターを使用するバインド要素を取得するには、この手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="67838-121">Also, to get a custom behavior or binding element to work with WCF-Custom adapter, complete these steps:</span></span>  
  
1.  <span data-ttu-id="67838-122">GAC アセンブリ</span><span class="sxs-lookup"><span data-stu-id="67838-122">GAC the assembly</span></span>  
  
2.  <span data-ttu-id="67838-123">Machine.config ファイルを変更 (で見つかった **%FrameworkDir%\v4.0.30319\CONFIG**)。</span><span class="sxs-lookup"><span data-stu-id="67838-123">Modify your machine.config file (found in **%FrameworkDir%\v4.0.30319\CONFIG**).</span></span>  
  
    1.  <span data-ttu-id="67838-124">動作のサービス構成エディター内で DLL を読み込む (**svcConfigEditor.exe**)。</span><span class="sxs-lookup"><span data-stu-id="67838-124">Load your behavior DLL inside the Service Configuration Editor (**svcConfigEditor.exe**).</span></span>  
  
    2.  <span data-ttu-id="67838-125">構成を保存、 **app.config**ファイル</span><span class="sxs-lookup"><span data-stu-id="67838-125">Save the configuration to an **app.config** file</span></span>  
  
    3.  <span data-ttu-id="67838-126">コピーして貼り付け、 **system.servicemodel** machine.config の同様のセクションの extensions セクション。場合**system.servicemodel**セクションがあります、machine.config に存在しない 1 つを作成します。</span><span class="sxs-lookup"><span data-stu-id="67838-126">Copy and paste the **system.servicemodel** extensions section in a similar section in machine.config. If **system.servicemodel** section is not present in machine.config, your must create one.</span></span> <span data-ttu-id="67838-127">Machine.config ファイルの構成セクションの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="67838-127">The following is an example from the configuration section of a machine.config file:</span></span>  
  
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
>  <span data-ttu-id="67838-128">上記のコードは、WCF 拡張機能 タブにも追加できます。場合は、拡張機能は、受信側である必要がありますを参照してください、 **\<ホスト名\>プロパティ ダイアログ ボックスで、WCF 拡張機能**タブ (Wcf-custom または Wcf-customisolated アダプターの受信ハンドラー)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="67838-128">The above code can also be added to the WCF Extensions tab. If the extension needs to be on the receive side, see the **\<Host Name\> Properties Dialog Box, WCF Extensions** tab (WCF-Custom or WCF-CustomIsolated Adapter Receive Handler) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="67838-129">表示拡張機能は、送信側である必要があります、 **\<ホスト名\>プロパティ ダイアログ ボックスで、WCF 拡張機能** タブ (Wcf-custom アダプターの送信ハンドラー)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="67838-129">If the extension needs to be on the send side, see **\<Host Name\> Properties Dialog Box, WCF Extensions** tab (WCF-Custom Adapter Send Handler) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 3. <span data-ttu-id="67838-130">管理コンソールを閉じてから。</span><span class="sxs-lookup"><span data-stu-id="67838-130">Close and reopen your admin console.</span></span> <span data-ttu-id="67838-131">WCF カスタム アダプターのカスタム動作を確認できるし、有効にすると、ポートを有効になっている維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67838-131">You should be able to see your custom behavior in the WCF-Custom adapter, and the port should stay enabled when you enable it.</span></span>