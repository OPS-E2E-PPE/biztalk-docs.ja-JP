---
title: シングル サインオン:イベント 10843 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 847e464e-5733-4703-905f-d44a4c4f5cc3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8389a1b6443fbe2d4abe592b305508b2780afdf6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307314"
---
# <a name="single-sign-on-event-10843"></a><span data-ttu-id="efc91-102">シングル サインオン:イベント 10843</span><span class="sxs-lookup"><span data-stu-id="efc91-102">Single Sign-On: Event 10843</span></span>
## <a name="details"></a><span data-ttu-id="efc91-103">詳細</span><span class="sxs-lookup"><span data-stu-id="efc91-103">Details</span></span>  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="efc91-104">製品名</span><span class="sxs-lookup"><span data-stu-id="efc91-104">Product Name</span></span>   |                                                                      <span data-ttu-id="efc91-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="efc91-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="efc91-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="efc91-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="efc91-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="efc91-107">Event ID</span></span>     |                                                                                <span data-ttu-id="efc91-108">10843</span><span class="sxs-lookup"><span data-stu-id="efc91-108">10843</span></span>                                                                                |
|  <span data-ttu-id="efc91-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="efc91-109">Event Source</span></span>   |                                                                               <span data-ttu-id="efc91-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="efc91-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="efc91-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="efc91-111">Component</span></span>    |                                                                                 <span data-ttu-id="efc91-112">なし</span><span class="sxs-lookup"><span data-stu-id="efc91-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="efc91-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="efc91-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="efc91-114">ENTSSO_E_NO_SECRET2</span><span class="sxs-lookup"><span data-stu-id="efc91-114">ENTSSO_E_NO_SECRET2</span></span>                                                                         |
|  <span data-ttu-id="efc91-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="efc91-115">Message Text</span></span>   | <span data-ttu-id="efc91-116">シークレットがマスター シークレット サーバーから利用できないために、暗号化または復号化を実行できません。</span><span class="sxs-lookup"><span data-stu-id="efc91-116">Cannot perform encryption or decryption because the secret is not available from the master secret server.</span></span> <span data-ttu-id="efc91-117">関連するエラーについては、(コンピュータ '%1') のイベント ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efc91-117">See the event log (on computer ‘%1’) for related errors.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="efc91-118">説明</span><span class="sxs-lookup"><span data-stu-id="efc91-118">Explanation</span></span>  
 <span data-ttu-id="efc91-119">アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="efc91-119">Access is denied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="efc91-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="efc91-120">User Action</span></span>  
 <span data-ttu-id="efc91-121">マスター シークレット サーバーがオフライン状態、またはいずれか、マスター シークレット サーバーに必要なマスター シークレットがありません。</span><span class="sxs-lookup"><span data-stu-id="efc91-121">Either the master secret server is off-line, or the master secret server is missing the required master secret.</span></span> <span data-ttu-id="efc91-122">関連するエラーの指定したコンピューター上のイベント ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efc91-122">See the event log on the specified computer for related errors.</span></span>