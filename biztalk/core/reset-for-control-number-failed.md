---
title: 失敗の制御番号のリセット |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e83c07-1569-4433-b882-a26784b7bb0f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 480a61535697d0b04fa106b4f7930a8a54362e0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996603"
---
# <a name="reset-for-control-number-failed"></a><span data-ttu-id="0ecb3-102">制御番号のリセットが失敗しました</span><span class="sxs-lookup"><span data-stu-id="0ecb3-102">Reset for Control number failed</span></span>
## <a name="details"></a><span data-ttu-id="0ecb3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0ecb3-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0ecb3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0ecb3-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0ecb3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0ecb3-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0ecb3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ecb3-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0ecb3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0ecb3-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0ecb3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0ecb3-108"> EDI</span></span> |
|    <span data-ttu-id="0ecb3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0ecb3-109">Component</span></span>    |                                       <span data-ttu-id="0ecb3-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="0ecb3-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="0ecb3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0ecb3-111">Symbolic Name</span></span>  |                              <span data-ttu-id="0ecb3-112">EdiControlNumberResetFailed</span><span class="sxs-lookup"><span data-stu-id="0ecb3-112">EdiControlNumberResetFailed</span></span>                               |
|  <span data-ttu-id="0ecb3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0ecb3-113">Message Text</span></span>   |                                 <span data-ttu-id="0ecb3-114">リセット{0}できませんでした。</span><span class="sxs-lookup"><span data-stu-id="0ecb3-114">Reset for {0} failed.</span></span>                                  |
  
 <span data-ttu-id="0ecb3-115">**{0}**: トランザクション セット制御番号/グループ制御番号/インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="0ecb3-115">**{0}**: Transaction Set Control number / Group Control number / Interchange Control number</span></span>  
  
## <a name="explanation"></a><span data-ttu-id="0ecb3-116">説明</span><span class="sxs-lookup"><span data-stu-id="0ecb3-116">Explanation</span></span>  
 <span data-ttu-id="0ecb3-117">このエラー/警告/情報イベントは、BizTalk Server が制御番号をリセットできなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0ecb3-117">This Error/Warning/Information event indicates BizTalk Server was not able to reset the control number.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ecb3-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0ecb3-118">User Action</span></span>  
 <span data-ttu-id="0ecb3-119">このエラーを解決するには、UI を再び開いてやり直してください。</span><span class="sxs-lookup"><span data-stu-id="0ecb3-119">To resolve this error, please reopen the UI and try again.</span></span>