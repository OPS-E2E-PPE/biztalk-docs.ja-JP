---
title: GS と GE のグループ制御番号が一致しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2419f61-2717-4347-a4be-54362330c7e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f162bdcfd76d25a37e196c37c25cbb970fb27155
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993635"
---
# <a name="group-control-number-in-gs-and-ge-do-not-match"></a><span data-ttu-id="7e556-102">GS と GE のグループ制御番号が一致しません</span><span class="sxs-lookup"><span data-stu-id="7e556-102">Group control number in GS and GE do not match</span></span>
## <a name="details"></a><span data-ttu-id="7e556-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7e556-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7e556-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7e556-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7e556-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7e556-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7e556-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7e556-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7e556-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7e556-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7e556-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7e556-108"> EDI</span></span> |
|    <span data-ttu-id="7e556-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7e556-109">Component</span></span>    |                                       <span data-ttu-id="7e556-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="7e556-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="7e556-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7e556-111">Symbolic Name</span></span>  |                         <span data-ttu-id="7e556-112">X12FaControlNumberMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="7e556-112">X12FaControlNumberMismatchDescription</span></span>                          |
|  <span data-ttu-id="7e556-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7e556-113">Message Text</span></span>   |                     <span data-ttu-id="7e556-114">GS と GE のグループ制御番号が一致しません</span><span class="sxs-lookup"><span data-stu-id="7e556-114">Group control number in GS and GE do not match</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="7e556-115">説明</span><span class="sxs-lookup"><span data-stu-id="7e556-115">Explanation</span></span>  
 <span data-ttu-id="7e556-116">このエラー/警告/情報イベントは、インターチェンジの GS06 および GE02 フィールドに含まれている制御番号の値が同じでないため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="7e556-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the control numbers contained in the GS06 and GE02 fields of the  interchange do not have the same value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7e556-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7e556-117">User Action</span></span>  
 <span data-ttu-id="7e556-118">このエラーを解決するには、インターチェンジの GS06 および GE02 フィールドに含まれているグループ制御番号の値が同じであることを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="7e556-118">To resolve this error, make sure that the group control numbers contained in the GS06 and GE02 fields of the interchange have the same value, and then have the interchange resent.</span></span>