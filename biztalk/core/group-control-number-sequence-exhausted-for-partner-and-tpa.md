---
title: "パートナーと TPA の制御番号シーケンスが終了をグループ化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf341f8d-02ec-4618-a980-c8ac90654b1a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1850b968a2c9b4c8d2c16fd90d9e37d80b60f8b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="group-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="b8f67-102">パートナーと TPA のグループ制御番号のシーケンスが終了しました</span><span class="sxs-lookup"><span data-stu-id="b8f67-102">Group control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="b8f67-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b8f67-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8f67-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b8f67-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b8f67-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b8f67-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b8f67-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b8f67-106">Event ID</span></span>|-|  
|<span data-ttu-id="b8f67-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b8f67-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b8f67-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="b8f67-108"> EDI</span></span>|  
|<span data-ttu-id="b8f67-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b8f67-109">Component</span></span>|<span data-ttu-id="b8f67-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="b8f67-110">EDI Engine</span></span>|  
|<span data-ttu-id="b8f67-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b8f67-111">Symbolic Name</span></span>|<span data-ttu-id="b8f67-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="b8f67-112">EdiControlNumberExhaustedForParty</span></span>|  
|<span data-ttu-id="b8f67-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b8f67-113">Message Text</span></span>|<span data-ttu-id="b8f67-114">グループ制御番号のシーケンスを使い果たすと、TPA '{2}' のパートナー '{1}' です。</span><span class="sxs-lookup"><span data-stu-id="b8f67-114">Group control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="b8f67-115">{2} - BizTalk Server 管理コンソールを使用して EDI プロパティでシーケンスをリセットします。</span><span class="sxs-lookup"><span data-stu-id="b8f67-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b8f67-116">説明</span><span class="sxs-lookup"><span data-stu-id="b8f67-116">Explanation</span></span>  
 <span data-ttu-id="b8f67-117">このエラー/警告/情報イベントは、BizTalk Server でのアグリーメントに {2} グループ制御の範囲が使い果たされたため、ドキュメントを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b8f67-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Group control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b8f67-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b8f67-118">User Action</span></span>  
 <span data-ttu-id="b8f67-119">このエラーを解決するのには、チェックを {2} アグリーメントの制御番号をリセットまたは制御番号の範囲を増やすか、アグリーメントでは、制御番号範囲指定に対するリセット ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8f67-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>