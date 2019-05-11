---
title: 無効な認証値 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70d0dd75-b045-4b67-ba23-78551493f074
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfb46cefaae04f6edc83ac570d8af73f8f806a95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381404"
---
# <a name="invalid-authorization-value"></a><span data-ttu-id="e0e0d-102">認証の値が無効です</span><span class="sxs-lookup"><span data-stu-id="e0e0d-102">Invalid Authorization Value</span></span>
## <a name="details"></a><span data-ttu-id="e0e0d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e0e0d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e0e0d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e0e0d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e0e0d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e0e0d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e0e0d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e0e0d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e0e0d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e0e0d-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e0e0d-108">EDI</span><span class="sxs-lookup"><span data-stu-id="e0e0d-108">EDI</span></span> |
|    <span data-ttu-id="e0e0d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e0e0d-109">Component</span></span>    |                                       <span data-ttu-id="e0e0d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e0e0d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e0e0d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e0e0d-111">Symbolic Name</span></span>  |                       <span data-ttu-id="e0e0d-112">X12Ta1InvalidAuthorizationValueDescription</span><span class="sxs-lookup"><span data-stu-id="e0e0d-112">X12Ta1InvalidAuthorizationValueDescription</span></span>                       |
|  <span data-ttu-id="e0e0d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e0e0d-113">Message Text</span></span>   |                              <span data-ttu-id="e0e0d-114">認証の値が無効です</span><span class="sxs-lookup"><span data-stu-id="e0e0d-114">Invalid Authorization Value</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="e0e0d-115">説明</span><span class="sxs-lookup"><span data-stu-id="e0e0d-115">Explanation</span></span>  
 <span data-ttu-id="e0e0d-116">このエラー/警告/情報イベントは、ISA02 の [認証情報] の値が、スキーマ (X12_AN) で指定されたデータ型に準拠していなかったか、またはスキーマ (10) で必要な桁数がなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e0e0d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the Authorization Information in ISA02 did not conform to the data type specified by the schema (X12_AN), or did not have the number of digits required by the schema (10).</span></span> <span data-ttu-id="e0e0d-117">スキーマは、BaseArtifacts.dll 内の X12ServiceSchema です。</span><span class="sxs-lookup"><span data-stu-id="e0e0d-117">The schema is the X12ServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e0e0d-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e0e0d-118">User Action</span></span>  
 <span data-ttu-id="e0e0d-119">このエラーを解決するには、ISA02 ヘッダーの値が X12:AN データ型に準拠し、末尾のスペースを含めて 10 桁であることを確認してから、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="e0e0d-119">To resolve this error, make sure that the value in the ISA02 header conforms to the X12:AN data type and has 10 digits (with trailing spaces), and then have the interchange resent.</span></span>