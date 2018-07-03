---
title: パートナーと TPA のインターチェンジ制御番号シーケンスが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e77c0574-bc51-4690-a7f6-5702f6486f05
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19f1aeb79febf8bca10f46b2b5a3a5ba319f6028
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989363"
---
# <a name="interchange-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="d2b2b-102">パートナーと TPA のインターチェンジ制御番号のシーケンスが終了しました</span><span class="sxs-lookup"><span data-stu-id="d2b2b-102">Interchange control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="d2b2b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d2b2b-103">Details</span></span>  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d2b2b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d2b2b-104">Product Name</span></span>   |                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
| <span data-ttu-id="d2b2b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d2b2b-105">Product Version</span></span> |                                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                     |
|    <span data-ttu-id="d2b2b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d2b2b-106">Event ID</span></span>     |                                                                                 -                                                                                  |
|  <span data-ttu-id="d2b2b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d2b2b-107">Event Source</span></span>   |                                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d2b2b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="d2b2b-108"> EDI</span></span>                                       |
|    <span data-ttu-id="d2b2b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d2b2b-109">Component</span></span>    |                                                                             <span data-ttu-id="d2b2b-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d2b2b-110">EDI Engine</span></span>                                                                             |
|  <span data-ttu-id="d2b2b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d2b2b-111">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="d2b2b-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="d2b2b-112">EdiControlNumberExhaustedForParty</span></span>                                                                  |
|  <span data-ttu-id="d2b2b-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d2b2b-113">Message Text</span></span>   | <span data-ttu-id="d2b2b-114">パートナーのインターチェンジ制御番号シーケンスが '{1}'for 'TPA{2}'。</span><span class="sxs-lookup"><span data-stu-id="d2b2b-114">Interchange control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="d2b2b-115">シーケンスをリセット{2}- BizTalk Server 管理コンソールを使用して EDI のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d2b2b-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d2b2b-116">説明</span><span class="sxs-lookup"><span data-stu-id="d2b2b-116">Explanation</span></span>  
 <span data-ttu-id="d2b2b-117">このエラー/警告/情報イベントは、インターチェンジ制御の範囲が {2} のアグリーメントにすべて使用されたため、BizTalk Server がドキュメントを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="d2b2b-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Interchange control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d2b2b-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d2b2b-118">User Action</span></span>  
 <span data-ttu-id="d2b2b-119">このエラーを解決するには、チェック ボックスをオンにして {2} アグリーメントの制御番号をリセットするか、制御番号の範囲を大きくするか、またはアグリーメントの制御番号範囲指定に対するリセット ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="d2b2b-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>