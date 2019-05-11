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
ms.openlocfilehash: ad35d7ddd35b6f21b2aef73cd7ddf12fe42ebcc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331695"
---
# <a name="interchange-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="8cd76-102">パートナーと TPA のインターチェンジ制御番号シーケンス</span><span class="sxs-lookup"><span data-stu-id="8cd76-102">Interchange control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="8cd76-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8cd76-103">Details</span></span>  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8cd76-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8cd76-104">Product Name</span></span>   |                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
| <span data-ttu-id="8cd76-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8cd76-105">Product Version</span></span> |                                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                     |
|    <span data-ttu-id="8cd76-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8cd76-106">Event ID</span></span>     |                                                                                 -                                                                                  |
|  <span data-ttu-id="8cd76-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8cd76-107">Event Source</span></span>   |                                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8cd76-108">EDI</span><span class="sxs-lookup"><span data-stu-id="8cd76-108">EDI</span></span>                                       |
|    <span data-ttu-id="8cd76-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8cd76-109">Component</span></span>    |                                                                             <span data-ttu-id="8cd76-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8cd76-110">EDI Engine</span></span>                                                                             |
|  <span data-ttu-id="8cd76-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8cd76-111">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="8cd76-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="8cd76-112">EdiControlNumberExhaustedForParty</span></span>                                                                  |
|  <span data-ttu-id="8cd76-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8cd76-113">Message Text</span></span>   | <span data-ttu-id="8cd76-114">パートナーのインターチェンジ制御番号シーケンスが '{1}'for 'TPA{2}'。</span><span class="sxs-lookup"><span data-stu-id="8cd76-114">Interchange control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="8cd76-115">シーケンスをリセット{2}- BizTalk Server 管理コンソールを使用して EDI のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="8cd76-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8cd76-116">説明</span><span class="sxs-lookup"><span data-stu-id="8cd76-116">Explanation</span></span>  
 <span data-ttu-id="8cd76-117">このエラー/警告/情報イベントは、BizTalk Server でのアグリーメントのインターチェンジ制御の範囲が使い果たされたために、ドキュメントを処理できなかったことを示します{2}します。</span><span class="sxs-lookup"><span data-stu-id="8cd76-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Interchange control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8cd76-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8cd76-118">User Action</span></span>  
 <span data-ttu-id="8cd76-119">このエラーを解決するのには、制御番号をリセットするチェック ボックスをオンしてください、{2}契約または増加コントロール番号の範囲または契約書に制御番号の範囲指定に対するリセット ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cd76-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>