---
title: 要素に無効な構造が |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb94843c-cd21-48e3-ba30-aed0518b4d78
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b626343ed00add57d6deab4b349a75b4df2164a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987701"
---
# <a name="the-element-has-an-invalid-structure"></a><span data-ttu-id="f944d-102">要素の構造が無効です</span><span class="sxs-lookup"><span data-stu-id="f944d-102">The element has an invalid structure</span></span>
## <a name="details"></a><span data-ttu-id="f944d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f944d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f944d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f944d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f944d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f944d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f944d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f944d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f944d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f944d-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f944d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f944d-108"> EDI</span></span> |
|    <span data-ttu-id="f944d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f944d-109">Component</span></span>    |                                       <span data-ttu-id="f944d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="f944d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="f944d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f944d-111">Symbolic Name</span></span>  |                      <span data-ttu-id="f944d-112">X12NseStructurallyInvalidElementDescription</span><span class="sxs-lookup"><span data-stu-id="f944d-112">X12NseStructurallyInvalidElementDescription</span></span>                       |
|  <span data-ttu-id="f944d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f944d-113">Message Text</span></span>   |                       <span data-ttu-id="f944d-114">要素 '{0}' が無効な構造</span><span class="sxs-lookup"><span data-stu-id="f944d-114">The element '{0}' has an invalid structure</span></span>                       |
  
## <a name="explanation"></a><span data-ttu-id="f944d-115">説明</span><span class="sxs-lookup"><span data-stu-id="f944d-115">Explanation</span></span>  
 <span data-ttu-id="f944d-116">このエラー/警告/情報イベントは、データ要素に、該当するスキーマで指定されている構造がなかったため、受信パイプラインで受信インターチェンジを処理できなかったか、または送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f944d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, or the send pipeline could not process the outgoing interchange, because a data element did not have the structure specified by the applicable schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f944d-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f944d-117">User Action</span></span>  
 <span data-ttu-id="f944d-118">このエラーを解決するには、送信インターチェンジのデータ要素の構造を修正するか、またはインターチェンジの送信者に対して、受信インターチェンジのデータ要素の構造を変更し、ドキュメント スキーマに準拠するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="f944d-118">To resolve this error, fix the structure of the data element in the outgoing interchange, or have the sender of the interchange fix the structure of the data element in the incoming interchange, so that it conforms to the document schema.</span></span>