---
title: トランザクション セット、サポートされているが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ffe8528-f34f-4189-8ee6-4ae1afb50c92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 908705bf733e7f95f771520ce9adee5a70dfe330
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279791"
---
# <a name="transaction-set-not-supported"></a><span data-ttu-id="568c3-102">トランザクション セットがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="568c3-102">Transaction Set Not Supported</span></span>
## <a name="details"></a><span data-ttu-id="568c3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="568c3-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="568c3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="568c3-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="568c3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="568c3-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="568c3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="568c3-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="568c3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="568c3-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="568c3-108">EDI</span><span class="sxs-lookup"><span data-stu-id="568c3-108">EDI</span></span> |
|    <span data-ttu-id="568c3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="568c3-109">Component</span></span>    |                                       <span data-ttu-id="568c3-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="568c3-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="568c3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="568c3-111">Symbolic Name</span></span>  |                              <span data-ttu-id="568c3-112">X12TsNotSupportedDescription</span><span class="sxs-lookup"><span data-stu-id="568c3-112">X12TsNotSupportedDescription</span></span>                              |
|  <span data-ttu-id="568c3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="568c3-113">Message Text</span></span>   |                             <span data-ttu-id="568c3-114">トランザクション セットがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="568c3-114">Transaction Set Not Supported</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="568c3-115">説明</span><span class="sxs-lookup"><span data-stu-id="568c3-115">Explanation</span></span>  
 <span data-ttu-id="568c3-116">このエラー/警告/情報イベントは、トランザクション セットのドキュメントの種類に応じたドキュメント スキーマが展開されていないため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="568c3-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a document schema has not been deployed for the document type of that transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="568c3-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="568c3-117">User Action</span></span>  
 <span data-ttu-id="568c3-118">このエラーを解決するには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、トランザクション セットのドキュメントの種類に応じたドキュメント スキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="568c3-118">To resolve this error, in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] deploy a document schema for the document type of the transaction set.</span></span>