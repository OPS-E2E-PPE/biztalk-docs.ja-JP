---
title: 無効な ASN.1 圧縮データ oid OID が見つかりません圧縮解除処理中に発生した |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0171daa8-289a-43f1-8cbf-d779ef9dc2ea
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d65dbf7d41612d6060516c20864d131207e7720
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388776"
---
# <a name="invalid-or-missing-asn1-compressed-data-oid-encountered-during-decompression-processing"></a><span data-ttu-id="366bb-102">圧縮解除処理中に無効な ASN.1 圧縮データ OID が検出されたか、ASN.1 圧縮データ OID が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="366bb-102">Invalid or missing ASN.1 Compressed Data OID encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="366bb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="366bb-103">Details</span></span>  
  
|                 |                                                                                          |
|-----------------|------------------------------------------------------------------------------------------|
|  <span data-ttu-id="366bb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="366bb-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="366bb-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="366bb-105">Product Version</span></span> |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    <span data-ttu-id="366bb-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="366bb-106">Event ID</span></span>     |                                            -                                             |
|  <span data-ttu-id="366bb-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="366bb-107">Event Source</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="366bb-108">EDI</span><span class="sxs-lookup"><span data-stu-id="366bb-108">EDI</span></span>  |
|    <span data-ttu-id="366bb-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="366bb-109">Component</span></span>    |                                        <span data-ttu-id="366bb-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="366bb-110">AS2 Engine</span></span>                                        |
|  <span data-ttu-id="366bb-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="366bb-111">Symbolic Name</span></span>  |                                            -                                             |
|  <span data-ttu-id="366bb-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="366bb-112">Message Text</span></span>   | <span data-ttu-id="366bb-113">圧縮解除処理中に無効な ASN.1 圧縮データ OID が検出されたか、ASN.1 圧縮データ OID が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="366bb-113">Invalid or missing ASN.1 Compressed Data OID encountered during decompression processing</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="366bb-114">説明</span><span class="sxs-lookup"><span data-stu-id="366bb-114">Explanation</span></span>  
 <span data-ttu-id="366bb-115">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="366bb-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="366bb-116">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="366bb-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="366bb-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="366bb-117">User Action</span></span>  
 <span data-ttu-id="366bb-118">圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="366bb-118">Review the structure of the compressed data and check for tampering with the message.</span></span>