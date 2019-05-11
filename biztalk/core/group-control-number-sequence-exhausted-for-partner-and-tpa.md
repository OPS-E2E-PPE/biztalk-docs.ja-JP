---
title: パートナーと TPA のグループの制御番号のシーケンスが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf341f8d-02ec-4618-a980-c8ac90654b1a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ff33fb039c1cd4e88e173bb657471ce9f2c738
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387589"
---
# <a name="group-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="078c6-102">グループ制御番号シーケンスがパートナーと TPA の</span><span class="sxs-lookup"><span data-stu-id="078c6-102">Group control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="078c6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="078c6-103">Details</span></span>  
  
|                 |                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="078c6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="078c6-104">Product Name</span></span>   |                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                      |
| <span data-ttu-id="078c6-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="078c6-105">Product Version</span></span> |                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                  |
|    <span data-ttu-id="078c6-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="078c6-106">Event ID</span></span>     |                                                                              -                                                                               |
|  <span data-ttu-id="078c6-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="078c6-107">Event Source</span></span>   |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="078c6-108">EDI</span><span class="sxs-lookup"><span data-stu-id="078c6-108">EDI</span></span>                                    |
|    <span data-ttu-id="078c6-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="078c6-109">Component</span></span>    |                                                                          <span data-ttu-id="078c6-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="078c6-110">EDI Engine</span></span>                                                                          |
|  <span data-ttu-id="078c6-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="078c6-111">Symbolic Name</span></span>  |                                                              <span data-ttu-id="078c6-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="078c6-112">EdiControlNumberExhaustedForParty</span></span>                                                               |
|  <span data-ttu-id="078c6-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="078c6-113">Message Text</span></span>   | <span data-ttu-id="078c6-114">パートナー グループ制御番号のシーケンスが '{1}'for 'TPA{2}'。</span><span class="sxs-lookup"><span data-stu-id="078c6-114">Group control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="078c6-115">シーケンスをリセット{2}- BizTalk Server 管理コンソールを使用して EDI のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="078c6-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="078c6-116">説明</span><span class="sxs-lookup"><span data-stu-id="078c6-116">Explanation</span></span>  
 <span data-ttu-id="078c6-117">このエラー/警告/情報イベントは、BizTalk Server でアグリーメントにグループ コントロールの範囲が使い果たされたために、ドキュメントを処理できなかったことを示します{2}します。</span><span class="sxs-lookup"><span data-stu-id="078c6-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Group control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="078c6-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="078c6-118">User Action</span></span>  
 <span data-ttu-id="078c6-119">このエラーを解決するのには、制御番号をリセットするチェック ボックスをオンしてください、{2}契約または増加コントロール番号の範囲または契約書に制御番号の範囲指定に対するリセット ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="078c6-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>