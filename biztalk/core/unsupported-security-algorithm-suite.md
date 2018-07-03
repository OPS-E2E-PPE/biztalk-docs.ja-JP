---
title: サポートされていないセキュリティ アルゴリズム スイート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11696fed-c3a8-4b11-8249-9f99f7abc8f2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32b00fea76b95a76cbb6b88f18056bba798e1381
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990987"
---
# <a name="unsupported-security-algorithm-suite"></a><span data-ttu-id="fe4f7-102">セキュリティ アルゴリズム スイートがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="fe4f7-102">Unsupported security algorithm suite</span></span>
## <a name="details"></a><span data-ttu-id="fe4f7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fe4f7-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="fe4f7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fe4f7-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="fe4f7-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fe4f7-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="fe4f7-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fe4f7-106">Event ID</span></span>     |                                         <span data-ttu-id="fe4f7-107">0</span><span class="sxs-lookup"><span data-stu-id="fe4f7-107">0</span></span>                                          |
|  <span data-ttu-id="fe4f7-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fe4f7-108">Event Source</span></span>   |                                         <span data-ttu-id="fe4f7-109">0</span><span class="sxs-lookup"><span data-stu-id="fe4f7-109">0</span></span>                                          |
|    <span data-ttu-id="fe4f7-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fe4f7-110">Component</span></span>    |                                         <span data-ttu-id="fe4f7-111">0</span><span class="sxs-lookup"><span data-stu-id="fe4f7-111">0</span></span>                                          |
|  <span data-ttu-id="fe4f7-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fe4f7-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="fe4f7-113">0</span><span class="sxs-lookup"><span data-stu-id="fe4f7-113">0</span></span>                                          |
|  <span data-ttu-id="fe4f7-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fe4f7-114">Message Text</span></span>   |                     <span data-ttu-id="fe4f7-115">サポートされていないセキュリティ アルゴリズム スイート。 {0}</span><span class="sxs-lookup"><span data-stu-id="fe4f7-115">Unsupported security algorithm suite: {0}</span></span>                      |

## <a name="explanation"></a><span data-ttu-id="fe4f7-116">説明</span><span class="sxs-lookup"><span data-stu-id="fe4f7-116">Explanation</span></span>  
 <span data-ttu-id="fe4f7-117">このエラーは、受信場所または送信ポートのセキュリティ アルゴリズム スイート プロパティが不適切な値に設定されているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-117">This error occurs when the security algorithm suite property of a receive location or send port is set to an incorrect value.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fe4f7-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fe4f7-118">User Action</span></span>  
 <span data-ttu-id="fe4f7-119">トランザクション プロトコル プロパティを有効な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-119">Ensure that transaction protocol property is set to a valid value.</span></span>  

1. <span data-ttu-id="fe4f7-120">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="fe4f7-121">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="fe4f7-122">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-122">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="fe4f7-123">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-123">Right-click the transport name.</span></span>  

5. <span data-ttu-id="fe4f7-124">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-124">Click **Properties**.</span></span>  

6. <span data-ttu-id="fe4f7-125">ポート**型**一覧で、 **Wcf-nettcp**します。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-125">In the port **Type** list, select **WCF-NetTcp**.</span></span>  

7. <span data-ttu-id="fe4f7-126">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-126">Click **Configure**.</span></span>  

8. <span data-ttu-id="fe4f7-127">**Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-127">In the **WCF-NetTcp Transport Properties** dialog box, click the **Security** tab.</span></span>  

9. <span data-ttu-id="fe4f7-128">**メッセージ セキュリティ**セクションでは、値を必ず**アルゴリズム スイート**が正しい。</span><span class="sxs-lookup"><span data-stu-id="fe4f7-128">In the **Message security** section, ensure that the values for **Algorithm suite** are correct.</span></span>
