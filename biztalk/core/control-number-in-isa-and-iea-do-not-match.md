---
title: ISA と IEA の制御番号が一致しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f9091ea-460b-464b-acd5-8dc0488b61e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1fa574e63444740e85cbdd9bf8ac411c495b24f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016230"
---
# <a name="control-number-in-isa-and-iea-do-not-match"></a><span data-ttu-id="4ca65-102">ISA と IEA の制御番号が一致しません</span><span class="sxs-lookup"><span data-stu-id="4ca65-102">Control Number in ISA and IEA do not match</span></span>
## <a name="details"></a><span data-ttu-id="4ca65-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4ca65-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="4ca65-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4ca65-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="4ca65-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4ca65-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="4ca65-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4ca65-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="4ca65-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4ca65-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4ca65-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="4ca65-108"> EDI</span></span> |
|    <span data-ttu-id="4ca65-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4ca65-109">Component</span></span>    |                                       <span data-ttu-id="4ca65-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="4ca65-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="4ca65-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4ca65-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="4ca65-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4ca65-112">Message Text</span></span>   |                       <span data-ttu-id="4ca65-113">ISA と IEA の制御番号が一致しません</span><span class="sxs-lookup"><span data-stu-id="4ca65-113">Control Number in ISA and IEA do not match</span></span>                       |
  
## <a name="explanation"></a><span data-ttu-id="4ca65-114">説明</span><span class="sxs-lookup"><span data-stu-id="4ca65-114">Explanation</span></span>  
 <span data-ttu-id="4ca65-115">このエラー/警告/情報イベントは、インターチェンジの ISA13 および IEA02 フィールドに含まれているインターチェンジ制御番号の値が同じでないため、AS2 受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="4ca65-115">This Error/Warning/Information event indicates that the AS2 receive pipeline could not process the incoming interchange because the interchange control numbers contained in the ISA13 and IEA02 fields of the interchange do not have the same value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4ca65-116">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4ca65-116">User Action</span></span>  
 <span data-ttu-id="4ca65-117">このエラーを解決するには、インターチェンジの ISA13 および IEA02 フィールドに含まれているインターチェンジ制御番号の値が同じであることを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="4ca65-117">To resolve this error, make sure that the interchange control numbers contained in the ISA13 and IEA02 fields of the interchange have the same value, and then have the interchange resent.</span></span>