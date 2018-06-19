---
title: DocType が設定されていないために、トランザクション セットの処理後に発生したエラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a323658c-77d8-4059-aa15-d88c08e5450d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 874b0229eecdd5fe9c046f69789c4708b9280031
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240266"
---
# <a name="error-encountered-after-processing-transaction-sets-because-doctype-was-not-set"></a><span data-ttu-id="6c3a6-102">DocType が設定されていないため、トランザクション セットの処理後にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="6c3a6-102">Error encountered after processing Transaction Set(s) because DocType was not set</span></span>
## <a name="details"></a><span data-ttu-id="6c3a6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6c3a6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6c3a6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6c3a6-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6c3a6-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6c3a6-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="6c3a6-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6c3a6-106">Event ID</span></span>|-|  
|<span data-ttu-id="6c3a6-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6c3a6-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6c3a6-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6c3a6-108"> EDI</span></span>|  
|<span data-ttu-id="6c3a6-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6c3a6-109">Component</span></span>|<span data-ttu-id="6c3a6-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6c3a6-110">EDI Engine</span></span>|  
|<span data-ttu-id="6c3a6-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6c3a6-111">Symbolic Name</span></span>|<span data-ttu-id="6c3a6-112">DocTypeNotSet</span><span class="sxs-lookup"><span data-stu-id="6c3a6-112">DocTypeNotSet</span></span>|  
|<span data-ttu-id="6c3a6-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6c3a6-113">Message Text</span></span>|<span data-ttu-id="6c3a6-114">{0} トランザクション セットを処理した後でエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6c3a6-114">Error encountered after processing {0} Transaction Set(s).</span></span> <span data-ttu-id="6c3a6-115">DocType が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="6c3a6-115">DocType was not set</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6c3a6-116">説明</span><span class="sxs-lookup"><span data-stu-id="6c3a6-116">Explanation</span></span>  
 <span data-ttu-id="6c3a6-117">このエラー/警告/情報イベントは、ST01 (X12 インターチェンジの場合) または UNH2.1 (EDIFACT インターチェンジの場合) がトランザクション セットに対して設定されなかったため、EDI 受信パイプラインで受信トランザクションを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="6c3a6-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming transaction set because ST01 (for an X12 interchange) or UNH2.1 (for an EDIFACT interchange) was not set for the transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6c3a6-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6c3a6-118">User Action</span></span>  
 <span data-ttu-id="6c3a6-119">このエラーを解決するには、エラーの発生したトランザクション セットに対する ST01 または UNH1 セグメントが、有効なドキュメントの種類に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6c3a6-119">To resolve this error, verify that the ST01 or UNH1 segment for the transaction set in error is set to a valid document type.</span></span>