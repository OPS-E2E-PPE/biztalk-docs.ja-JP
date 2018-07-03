---
title: データ要素が長すぎます |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf608cc1-d482-4e19-8f56-10d9e03feb79
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 134c2c2b0931373840cf5726d8f6680590840b9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988739"
---
# <a name="data-element-too-long"></a><span data-ttu-id="a8a96-102">データ要素が長すぎます。</span><span class="sxs-lookup"><span data-stu-id="a8a96-102">Data element too long</span></span>
## <a name="details"></a><span data-ttu-id="a8a96-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a8a96-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a8a96-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a8a96-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a8a96-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a8a96-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a8a96-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a8a96-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a8a96-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a8a96-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a8a96-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="a8a96-108"> EDI</span></span> |
|    <span data-ttu-id="a8a96-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a8a96-109">Component</span></span>    |                                       <span data-ttu-id="a8a96-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="a8a96-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="a8a96-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a8a96-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="a8a96-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a8a96-112">Message Text</span></span>   |                                 <span data-ttu-id="a8a96-113">データ要素が長すぎます。</span><span class="sxs-lookup"><span data-stu-id="a8a96-113">Data element too long</span></span>                                  |
  
## <a name="explanation"></a><span data-ttu-id="a8a96-114">説明</span><span class="sxs-lookup"><span data-stu-id="a8a96-114">Explanation</span></span>  
 <span data-ttu-id="a8a96-115">このエラー/警告/情報イベントは、データ要素が、スキーマで指定されている最大の長さよりも長かったため、EDI 受信パイプラインまたは EDI 送信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a8a96-115">This Error/Warning/Information event indicates that the EDI receive pipeline or the EDI Send pipeline could not process the incoming interchange because a data element was longer than the maximum length specified by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8a96-116">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a8a96-116">User Action</span></span>  
 <span data-ttu-id="a8a96-117">このエラーを解決するには、インターチェンジの長すぎたデータ要素を変更し、上限より短くなるようにします。</span><span class="sxs-lookup"><span data-stu-id="a8a96-117">To resolve this error, shorten the data element in the interchange that was too long so it is below the maximum limit.</span></span> <span data-ttu-id="a8a96-118">最大の長さを確認するには、\XSD_Schema フォルダーのスキーマを開き、データ要素の ID を検索して、maxLength の値を調べます。</span><span class="sxs-lookup"><span data-stu-id="a8a96-118">To determine the maximum length, open the schema in the \XSD_Schema folder, search on the data element ID, and identify what the maxLength value is.</span></span>