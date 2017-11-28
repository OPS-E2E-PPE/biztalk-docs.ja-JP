---
title: "スキーマにルート要素が含まれていない |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efc33f2b-9e14-4d2e-8c8a-32b7696f80ea
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c485ce27fc3a1932d7de47557080712e46b654e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-schema-does-not-contain-the-root-element"></a><span data-ttu-id="9d43f-102">スキーマにルート要素が含まれていません</span><span class="sxs-lookup"><span data-stu-id="9d43f-102">The schema does not contain the root element</span></span>
## <a name="details"></a><span data-ttu-id="9d43f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9d43f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d43f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9d43f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9d43f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9d43f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9d43f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9d43f-106">Event ID</span></span>|-|  
|<span data-ttu-id="9d43f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9d43f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9d43f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9d43f-108"> EDI</span></span>|  
|<span data-ttu-id="9d43f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9d43f-109">Component</span></span>|<span data-ttu-id="9d43f-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="9d43f-110">EDI Engine</span></span>|  
|<span data-ttu-id="9d43f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9d43f-111">Symbolic Name</span></span>|<span data-ttu-id="9d43f-112">SchemaCode102ENullRootElement</span><span class="sxs-lookup"><span data-stu-id="9d43f-112">SchemaCode102ENullRootElement</span></span>|  
|<span data-ttu-id="9d43f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9d43f-113">Message Text</span></span>|<span data-ttu-id="9d43f-114">スキーマにルート要素 {0} が含まれていません</span><span class="sxs-lookup"><span data-stu-id="9d43f-114">The schema does not contain the root element {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9d43f-115">説明</span><span class="sxs-lookup"><span data-stu-id="9d43f-115">Explanation</span></span>  
 <span data-ttu-id="9d43f-116">このエラー/警告/情報イベントは、メッセージの検証に使用されるスキーマにルート要素が含まれていなかったため、受信パイプラインで受信メッセージを処理できなかったか、または送信パイプラインで送信メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="9d43f-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming message or the send pipeline could not process the outgoing message because the schema used to validate the message did not contain the root element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9d43f-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9d43f-117">User Action</span></span>  
 <span data-ttu-id="9d43f-118">このエラーを解決するには、ドキュメント スキーマの展開を解除し、ルート要素をスキーマに追加して、スキーマを再展開します。</span><span class="sxs-lookup"><span data-stu-id="9d43f-118">To resolve this error, undeploy the document schema, add the root element to the schema, and then redeploy the schema.</span></span>