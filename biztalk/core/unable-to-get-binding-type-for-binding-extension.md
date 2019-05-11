---
title: バインド拡張機能のバインドの種類を取得できません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7cfc81-7439-48f9-8cac-42b2419ecd9d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15a55bc8f06465daec562624866ed41a43059a05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292789"
---
# <a name="unable-to-get-binding-type-for-binding-extension"></a><span data-ttu-id="cfdbe-102">バインド拡張機能のバインドの種類を取得できません</span><span class="sxs-lookup"><span data-stu-id="cfdbe-102">Unable to get binding type for binding extension</span></span>
## <a name="details"></a><span data-ttu-id="cfdbe-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cfdbe-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cfdbe-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cfdbe-104">Product Name</span></span>   |                                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                        |
| <span data-ttu-id="cfdbe-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cfdbe-105">Product Version</span></span> |                                                                                    [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                    |
|    <span data-ttu-id="cfdbe-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cfdbe-106">Event ID</span></span>     |                                                                                                                <span data-ttu-id="cfdbe-107">0</span><span class="sxs-lookup"><span data-stu-id="cfdbe-107">0</span></span>                                                                                                                 |
|  <span data-ttu-id="cfdbe-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cfdbe-108">Event Source</span></span>   |                                                                                                                <span data-ttu-id="cfdbe-109">0</span><span class="sxs-lookup"><span data-stu-id="cfdbe-109">0</span></span>                                                                                                                 |
|    <span data-ttu-id="cfdbe-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cfdbe-110">Component</span></span>    |                                                                                                                <span data-ttu-id="cfdbe-111">0</span><span class="sxs-lookup"><span data-stu-id="cfdbe-111">0</span></span>                                                                                                                 |
|  <span data-ttu-id="cfdbe-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cfdbe-112">Symbolic Name</span></span>  |                                                                                                                <span data-ttu-id="cfdbe-113">0</span><span class="sxs-lookup"><span data-stu-id="cfdbe-113">0</span></span>                                                                                                                 |
|  <span data-ttu-id="cfdbe-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cfdbe-114">Message Text</span></span>   | <span data-ttu-id="cfdbe-115">バインド拡張機能のバインドの種類を取得できません。"{0}"。</span><span class="sxs-lookup"><span data-stu-id="cfdbe-115">Unable to get binding type for binding extension "{0}".</span></span> <span data-ttu-id="cfdbe-116">Machine.config が更新されたは、アプリケーションが開いているときに場合、は、変更内容を取得するアプリケーションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="cfdbe-116">If machine.config was updated while your application was open, restart your application to pick up changes.</span></span> <span data-ttu-id="cfdbe-117">バインド拡張機能が machine.config に登録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cfdbe-117">Verify the binding extension is registered in machine.config</span></span> |

## <a name="explanation"></a><span data-ttu-id="cfdbe-118">説明</span><span class="sxs-lookup"><span data-stu-id="cfdbe-118">Explanation</span></span>  
 <span data-ttu-id="cfdbe-119">Wcf-custom または Wcf-customisolated トランスポートのカスタム バインド拡張機能が正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="cfdbe-119">A custom binding extension for a WCF-Custom or a WCF-CustomIsolated transport was not configured properly.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cfdbe-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cfdbe-120">User Action</span></span>  
 <span data-ttu-id="cfdbe-121">このエラーは解決するのには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cfdbe-121">To resolve this error do one or more of the following:</span></span>  

- <span data-ttu-id="cfdbe-122">確認、 **machine.config ファイル**で **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config**が、 \< **bindingExtensions** \>要素が適切に構成します。</span><span class="sxs-lookup"><span data-stu-id="cfdbe-122">Ensure the **machine.config file** in **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config** has the \<**bindingExtensions**\> element configured properly.</span></span>  

- <span data-ttu-id="cfdbe-123">Windows エクスプ ローラーに移動 **%WinDir%\Assembly**、カスタム バインド拡張機能を実装するアセンブリが正しくインストールされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="cfdbe-123">In Windows Explorer, go to **%WinDir%\Assembly**, and make sure the assemblies implementing the custom binding extension are installed properly.</span></span>  

- <span data-ttu-id="cfdbe-124">WCF カスタム アダプターの場合、BizTalk 管理コンソールで、WCF トランスポートを実行するホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="cfdbe-124">For the WCF-Custom adapter, in the BizTalk Administration console, restart the host instance running the WCF transport.</span></span>  

- <span data-ttu-id="cfdbe-125">Wcf-customisolated アダプターの場合、IIS 管理コンソールで、WCF トランスポートをホストしているアプリケーション プールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="cfdbe-125">For the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool hosting the WCF transport.</span></span>  

- <span data-ttu-id="cfdbe-126">開かれた場合、BizTalk 管理コンソールの開閉</span><span class="sxs-lookup"><span data-stu-id="cfdbe-126">Open and close the BizTalk Administration console if it was opened</span></span>  

  <span data-ttu-id="cfdbe-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfdbe-127">For further information, see the following resource:</span></span>  

- [<span data-ttu-id="cfdbe-128">WCF アダプターで WCF 機能拡張ポイントを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="cfdbe-128">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)
