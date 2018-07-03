---
title: 無効な末尾に ASN.1 CMS 圧縮構造バイト圧縮解除処理中に |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b73ce58-d827-4ffc-b2d7-78836298efc8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 768fb1aa2ada6fb6c585e29db1f19cf04a1bd118
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991315"
---
# <a name="invalid-or-missing-trailing-asn1-cms-compressed-structure-bytes-during-decompression-processing"></a><span data-ttu-id="00b2d-102">圧縮解除処理中に ASN.1 CMS 圧縮構造の末尾に無効なバイトが検出されたか、バイトが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="00b2d-102">Invalid or missing trailing ASN.1 CMS compressed structure bytes during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="00b2d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="00b2d-103">Details</span></span>  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="00b2d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="00b2d-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| <span data-ttu-id="00b2d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="00b2d-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    <span data-ttu-id="00b2d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="00b2d-106">Event ID</span></span>     |                                                -                                                 |
|  <span data-ttu-id="00b2d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="00b2d-107">Event Source</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="00b2d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="00b2d-108"> EDI</span></span>      |
|    <span data-ttu-id="00b2d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="00b2d-109">Component</span></span>    |                                            <span data-ttu-id="00b2d-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="00b2d-110">AS2 Engine</span></span>                                            |
|  <span data-ttu-id="00b2d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="00b2d-111">Symbolic Name</span></span>  |                                                -                                                 |
|  <span data-ttu-id="00b2d-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="00b2d-112">Message Text</span></span>   | <span data-ttu-id="00b2d-113">圧縮解除処理中に ASN.1 CMS 圧縮構造の末尾に無効なバイトが検出されたか、バイトが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="00b2d-113">Invalid or missing trailing ASN.1 CMS compressed structure bytes during decompression processing</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="00b2d-114">説明</span><span class="sxs-lookup"><span data-stu-id="00b2d-114">Explanation</span></span>  
 <span data-ttu-id="00b2d-115">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="00b2d-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="00b2d-116">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="00b2d-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00b2d-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="00b2d-117">User Action</span></span>  
 <span data-ttu-id="00b2d-118">圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="00b2d-118">Review the structure of the compressed data and check for tampering with the message.</span></span>