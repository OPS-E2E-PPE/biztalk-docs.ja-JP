---
title: データ要素が短すぎます |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a22c0551-3262-476c-a6c6-2fd214331244
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db14770404a45ddbfd3aea6ed71e9b8b22417515
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005299"
---
# <a name="data-element-too-short"></a><span data-ttu-id="e20cc-102">データ要素が短すぎます。</span><span class="sxs-lookup"><span data-stu-id="e20cc-102">Data element too short</span></span>
## <a name="details"></a><span data-ttu-id="e20cc-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e20cc-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e20cc-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e20cc-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e20cc-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e20cc-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e20cc-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e20cc-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e20cc-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e20cc-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e20cc-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e20cc-108"> EDI</span></span> |
|    <span data-ttu-id="e20cc-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e20cc-109">Component</span></span>    |                                       <span data-ttu-id="e20cc-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e20cc-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e20cc-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e20cc-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="e20cc-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e20cc-112">Message Text</span></span>   |                                 <span data-ttu-id="e20cc-113">データ要素が短すぎます。</span><span class="sxs-lookup"><span data-stu-id="e20cc-113">Data element too short</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="e20cc-114">説明</span><span class="sxs-lookup"><span data-stu-id="e20cc-114">Explanation</span></span>  
 <span data-ttu-id="e20cc-115">このエラー/警告/情報イベントは、データ要素が、スキーマで指定されている最小の長さよりも短かったため、EDI 受信パイプラインまたは EDI 送信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e20cc-115">This Error/Warning/Information event indicates that the EDI receive pipeline or the EDI Send pipeline could not process the incoming interchange because a data element was shorter than the minimum length specified by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e20cc-116">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e20cc-116">User Action</span></span>  
 <span data-ttu-id="e20cc-117">このエラーを解決するには、インターチェンジの短すぎたデータ要素の長さを変更し、最小の長さよりも長くなるようにします。</span><span class="sxs-lookup"><span data-stu-id="e20cc-117">To resolve this error, lengthen the data element in the interchange that was too short so it is greater than the minimum length.</span></span> <span data-ttu-id="e20cc-118">最小の長さを確認するには、\XSD_Schema フォルダーのスキーマを開き、データ要素の ID を検索して、minLength の値を調べます。</span><span class="sxs-lookup"><span data-stu-id="e20cc-118">To determine the minimum length, open the schema in the \XSD_Schema folder, search on the data element ID, and identify what the minLength value is.</span></span>