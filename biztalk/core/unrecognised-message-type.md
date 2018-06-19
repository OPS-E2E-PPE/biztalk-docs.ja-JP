---
title: 認識できないメッセージの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4094bf-af00-4d5c-9661-7c8abcb1b722
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd58907b61e68140ccf68d8256882b81e46bd863
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286802"
---
# <a name="unrecognised-message-type"></a><span data-ttu-id="17d52-102">メッセージの種類が認識されていません</span><span class="sxs-lookup"><span data-stu-id="17d52-102">Unrecognised message type</span></span>
## <a name="details"></a><span data-ttu-id="17d52-103">詳細</span><span class="sxs-lookup"><span data-stu-id="17d52-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="17d52-104">製品名</span><span class="sxs-lookup"><span data-stu-id="17d52-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="17d52-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="17d52-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="17d52-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="17d52-106">Event ID</span></span>|-|  
|<span data-ttu-id="17d52-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="17d52-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="17d52-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="17d52-108"> EDI</span></span>|  
|<span data-ttu-id="17d52-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="17d52-109">Component</span></span>|<span data-ttu-id="17d52-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="17d52-110">EDI Engine</span></span>|  
|<span data-ttu-id="17d52-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="17d52-111">Symbolic Name</span></span>|<span data-ttu-id="17d52-112">UnRecognizedMessageType</span><span class="sxs-lookup"><span data-stu-id="17d52-112">UnRecognizedMessageType</span></span>|  
|<span data-ttu-id="17d52-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="17d52-113">Message Text</span></span>|<span data-ttu-id="17d52-114">メッセージの種類が認識されていません。</span><span class="sxs-lookup"><span data-stu-id="17d52-114">Unrecognised message type.</span></span> <span data-ttu-id="17d52-115">続行できません。</span><span class="sxs-lookup"><span data-stu-id="17d52-115">Cannot proceed further.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="17d52-116">説明</span><span class="sxs-lookup"><span data-stu-id="17d52-116">Explanation</span></span>  
 <span data-ttu-id="17d52-117">このエラー/警告/情報イベントは、対象のインターチェンジにおいてトランザクション セットのドキュメントの種類に応じたドキュメント スキーマが展開されていないか、または BizTalk Server が、トランザクション セットの識別子コード、バージョン、および名前空間からドキュメントの種類を判別できないため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="17d52-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because no document schema has been deployed for the document type of a transaction set in that interchange, or BizTalk Server cannot determine the document type from the transaction set identifier code, version, and namespace.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="17d52-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="17d52-118">User Action</span></span>  
 <span data-ttu-id="17d52-119">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="17d52-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="17d52-120">インターチェンジのトランザクション セットのドキュメントの種類に応じたドキュメント スキーマを展開し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="17d52-120">Deploy a document schema for the document type of a transaction set in the interchange, and then resend the interchange.</span></span>  
  
-   <span data-ttu-id="17d52-121">次の値が有効なスキーマを定義することを確認してください: x12 の場合、ターゲットの名前空間、バージョン/リリース、およびドキュメントを入力します。edifact の場合、ターゲットの名前空間、メッセージのバージョン番号、メッセージのリリース番号、およびメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="17d52-121">Verify that the following values define a valid schema: for X12, the target namespace, version/release, and document type; for EDIFACT, the target namespace, message version number, message release number, and message type.</span></span> <span data-ttu-id="17d52-122">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの「受信した EDI メッセージのパーティの解決、スキーマ探索、および認証」トピックで、「スキーマ探索」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17d52-122">For more information, see the "Schema Discovery" section in the "Party Resolution, Schema Discovery, and Authorization for Received EDI Messages" topic in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>