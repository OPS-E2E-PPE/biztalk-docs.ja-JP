---
title: 無効または見つからない ASN.1 圧縮ヘッダー圧縮解除処理中に発生した |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e59afea-436c-42c0-b424-0b72dd9db9a8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5847e077958a334704248bbc9c8cc21c2bb03d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241818"
---
# <a name="invalid-or-missing-asn1-compressed-header-encountered-during-decompression-processing"></a><span data-ttu-id="21fe5-102">圧縮解除処理中に無効な ASN.1 圧縮ヘッダーが検出されたか、ASN.1 圧縮ヘッダーが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="21fe5-102">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="21fe5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="21fe5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21fe5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="21fe5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="21fe5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="21fe5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="21fe5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="21fe5-106">Event ID</span></span>|-|  
|<span data-ttu-id="21fe5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="21fe5-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="21fe5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="21fe5-108"> EDI</span></span>|  
|<span data-ttu-id="21fe5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="21fe5-109">Component</span></span>|<span data-ttu-id="21fe5-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="21fe5-110">AS2 Engine</span></span>|  
|<span data-ttu-id="21fe5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="21fe5-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="21fe5-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="21fe5-112">Message Text</span></span>|<span data-ttu-id="21fe5-113">圧縮解除処理中に無効な ASN.1 圧縮ヘッダーが検出されたか、ASN.1 圧縮ヘッダーが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="21fe5-113">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="21fe5-114">説明</span><span class="sxs-lookup"><span data-stu-id="21fe5-114">Explanation</span></span>  
 <span data-ttu-id="21fe5-115">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="21fe5-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="21fe5-116">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="21fe5-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="21fe5-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="21fe5-117">User Action</span></span>  
 <span data-ttu-id="21fe5-118">圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="21fe5-118">Review the structure of the compressed data and check for tampering with the message.</span></span>