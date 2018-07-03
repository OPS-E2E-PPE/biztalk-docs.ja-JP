---
title: 無効な ASN.1 ZLib 圧縮フィールドが圧縮解除処理中に発生した |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7caf047-badd-49e8-b955-554e5ec7511f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ee1388304eb9923dcd2c6fef1468794f7c622a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012851"
---
# <a name="invalid-asn1-zlib-compression-field-encountered-during-decompression-processing"></a><span data-ttu-id="41adb-102">圧縮解除中に無効な ASN.1 ZLib 圧縮フィールドが検出されました</span><span class="sxs-lookup"><span data-stu-id="41adb-102">Invalid ASN.1 ZLib compression field encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="41adb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="41adb-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="41adb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="41adb-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="41adb-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="41adb-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="41adb-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="41adb-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="41adb-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="41adb-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="41adb-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="41adb-108"> EDI</span></span> |
|    <span data-ttu-id="41adb-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="41adb-109">Component</span></span>    |                                       <span data-ttu-id="41adb-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="41adb-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="41adb-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="41adb-111">Symbolic Name</span></span>  |                          <span data-ttu-id="41adb-112">InvalidOptionalZLibFieldEncountered</span><span class="sxs-lookup"><span data-stu-id="41adb-112">InvalidOptionalZLibFieldEncountered</span></span>                           |
|  <span data-ttu-id="41adb-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="41adb-113">Message Text</span></span>   |    <span data-ttu-id="41adb-114">圧縮解除中に無効な ASN.1 ZLib 圧縮フィールドが検出されました</span><span class="sxs-lookup"><span data-stu-id="41adb-114">Invalid ASN.1 ZLib compression field encountered during decompression processing</span></span>    |
  
## <a name="explanation"></a><span data-ttu-id="41adb-115">説明</span><span class="sxs-lookup"><span data-stu-id="41adb-115">Explanation</span></span>  
 <span data-ttu-id="41adb-116">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="41adb-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="41adb-117">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="41adb-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="41adb-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="41adb-118">User Action</span></span>  
 <span data-ttu-id="41adb-119">圧縮データの構造を見直し、改ざんの形跡がないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="41adb-119">Review the structure of the compressed data and check for evidence of tampering.</span></span>