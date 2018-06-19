---
title: パートナーと TPA のインターチェンジの制御番号シーケンスが終了 |Microsoft ドキュメント
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
ms.openlocfilehash: b4744a8db00985db3e85c1cb8843f07b3488544b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257042"
---
# <a name="interchange-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="f451b-102">パートナーと TPA のインターチェンジ制御番号のシーケンスが終了しました</span><span class="sxs-lookup"><span data-stu-id="f451b-102">Interchange control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="f451b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f451b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f451b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f451b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f451b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f451b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f451b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f451b-106">Event ID</span></span>|-|  
|<span data-ttu-id="f451b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f451b-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f451b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f451b-108"> EDI</span></span>|  
|<span data-ttu-id="f451b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f451b-109">Component</span></span>|<span data-ttu-id="f451b-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="f451b-110">EDI Engine</span></span>|  
|<span data-ttu-id="f451b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f451b-111">Symbolic Name</span></span>|<span data-ttu-id="f451b-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="f451b-112">EdiControlNumberExhaustedForParty</span></span>|  
|<span data-ttu-id="f451b-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f451b-113">Message Text</span></span>|<span data-ttu-id="f451b-114">TPA '{2}' のパートナー '{1}' を終了してインターチェンジ制御番号のシーケンス。</span><span class="sxs-lookup"><span data-stu-id="f451b-114">Interchange control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="f451b-115">{2} - BizTalk Server 管理コンソールを使用して EDI プロパティでシーケンスをリセットします。</span><span class="sxs-lookup"><span data-stu-id="f451b-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f451b-116">説明</span><span class="sxs-lookup"><span data-stu-id="f451b-116">Explanation</span></span>  
 <span data-ttu-id="f451b-117">このエラー/警告/情報イベントは、BizTalk Server で {2} でアグリーメントのインターチェンジ制御の範囲が使い果たされたため、ドキュメントを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f451b-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Interchange control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f451b-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f451b-118">User Action</span></span>  
 <span data-ttu-id="f451b-119">このエラーを解決するのには、チェックを {2} アグリーメントの制御番号をリセットまたは制御番号の範囲を増やすか、アグリーメントでは、制御番号範囲指定に対するリセット ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f451b-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>