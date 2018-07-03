---
title: 圧縮解除処理中に発生した ASN.1 データ長フィールドが無効か存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd08648d-77b9-42a3-a50e-fd87eb36758a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aaab2fa12fc9d175c237224128055081d596962
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994475"
---
# <a name="invalid-or-missing-asn1-data-length-field-encountered-during-decompression-processing"></a><span data-ttu-id="11942-102">圧縮解除中に無効な ASN.1 データ長フィールドが検出されたか、ASN.1 データ長フィールドが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="11942-102">Invalid or missing ASN.1 Data Length field encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="11942-103">詳細</span><span class="sxs-lookup"><span data-stu-id="11942-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="11942-104">製品名</span><span class="sxs-lookup"><span data-stu-id="11942-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="11942-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="11942-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="11942-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="11942-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="11942-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="11942-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="11942-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="11942-108"> EDI</span></span> |
|    <span data-ttu-id="11942-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="11942-109">Component</span></span>    |                                       <span data-ttu-id="11942-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="11942-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="11942-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="11942-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="11942-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="11942-112">Message Text</span></span>   | <span data-ttu-id="11942-113">圧縮解除中に無効な ASN.1 データ長フィールドが検出されたか、ASN.1 データ長フィールドが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="11942-113">Invalid or missing ASN.1 Data Length field encountered during decompression processing</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="11942-114">説明</span><span class="sxs-lookup"><span data-stu-id="11942-114">Explanation</span></span>  
 <span data-ttu-id="11942-115">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="11942-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="11942-116">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="11942-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="11942-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="11942-117">User Action</span></span>  
 <span data-ttu-id="11942-118">圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="11942-118">Review the structure of the compressed data and check for tampering with the message.</span></span>