---
title: シリアル化中に発生したエラーです。 X12 インターチェンジで次のエラーが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9ca3314-6c66-4400-816a-f9c7c7915122
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12ddd3879581387e776728a35b045ae1ac36a2b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388905"
---
# <a name="error-encountered-during-serialization-the-x12-interchange-had-the-following-errors"></a><span data-ttu-id="7adf2-103">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="7adf2-103">Error encountered during serialization.</span></span> <span data-ttu-id="7adf2-104">X12 インターチェンジで次のエラーが見つかりました</span><span class="sxs-lookup"><span data-stu-id="7adf2-104">The X12 interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="7adf2-105">詳細</span><span class="sxs-lookup"><span data-stu-id="7adf2-105">Details</span></span>  
  
|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7adf2-106">製品名</span><span class="sxs-lookup"><span data-stu-id="7adf2-106">Product Name</span></span>   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| <span data-ttu-id="7adf2-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7adf2-107">Product Version</span></span> |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    <span data-ttu-id="7adf2-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7adf2-108">Event ID</span></span>     |                                                                      -                                                                      |
|  <span data-ttu-id="7adf2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7adf2-109">Event Source</span></span>   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7adf2-110">EDI</span><span class="sxs-lookup"><span data-stu-id="7adf2-110">EDI</span></span>                            |
|    <span data-ttu-id="7adf2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7adf2-111">Component</span></span>    |                                                                 <span data-ttu-id="7adf2-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="7adf2-112">EDI Engine</span></span>                                                                  |
|  <span data-ttu-id="7adf2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7adf2-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="7adf2-114">X12InterchangeSendError</span><span class="sxs-lookup"><span data-stu-id="7adf2-114">X12InterchangeSendError</span></span>                                                           |
|  <span data-ttu-id="7adf2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7adf2-115">Message Text</span></span>   | <span data-ttu-id="7adf2-116">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="7adf2-116">Error encountered during serialization.</span></span> <span data-ttu-id="7adf2-117">X12 インターチェンジ id '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="7adf2-117">The X12 interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7adf2-118">説明</span><span class="sxs-lookup"><span data-stu-id="7adf2-118">Explanation</span></span>  
 <span data-ttu-id="7adf2-119">このエラー/警告/情報イベントは、EDI 送信パイプラインでは、X12 の送信をシリアル化するときに、エラーが発生したことを示します、示されたエラーのために交換します。</span><span class="sxs-lookup"><span data-stu-id="7adf2-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing X12 interchange because of the stated errors.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7adf2-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7adf2-120">User Action</span></span>  
 <span data-ttu-id="7adf2-121">このエラーを解決するには、エラー メッセージの情報を使用して、インターチェンジでエラーを特定し、製品のヘルプで問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="7adf2-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>