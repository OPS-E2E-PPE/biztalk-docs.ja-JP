---
title: シングル サインオン:イベント 10808 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4efc1d-f163-4440-a78e-53065c6af36c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae819cd41cc39b4866ae2d9befc0edc3952cb5b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380018"
---
# <a name="single-sign-on-event-10808"></a><span data-ttu-id="3a2aa-102">シングル サインオン:イベント 10808</span><span class="sxs-lookup"><span data-stu-id="3a2aa-102">Single Sign-On: Event 10808</span></span>
## <a name="details"></a><span data-ttu-id="3a2aa-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3a2aa-103">Details</span></span>  
  
|                 |                                                                  |
|-----------------|------------------------------------------------------------------|
|  <span data-ttu-id="3a2aa-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3a2aa-104">Product Name</span></span>   |                    <span data-ttu-id="3a2aa-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3a2aa-105">Enterprise Single Sign-On</span></span>                     |
| <span data-ttu-id="3a2aa-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3a2aa-106">Product Version</span></span> |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]    |
|    <span data-ttu-id="3a2aa-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3a2aa-107">Event ID</span></span>     |                              <span data-ttu-id="3a2aa-108">10808</span><span class="sxs-lookup"><span data-stu-id="3a2aa-108">10808</span></span>                               |
|  <span data-ttu-id="3a2aa-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3a2aa-109">Event Source</span></span>   |                              <span data-ttu-id="3a2aa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3a2aa-110">ENTSSO</span></span>                              |
|    <span data-ttu-id="3a2aa-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3a2aa-111">Component</span></span>    |                               <span data-ttu-id="3a2aa-112">なし</span><span class="sxs-lookup"><span data-stu-id="3a2aa-112">N/A</span></span>                                |
|  <span data-ttu-id="3a2aa-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3a2aa-113">Symbolic Name</span></span>  |                <span data-ttu-id="3a2aa-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="3a2aa-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span></span>                 |
|  <span data-ttu-id="3a2aa-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3a2aa-115">Message Text</span></span>   | <span data-ttu-id="3a2aa-116">ホスト側開始シングル サインオンは、SSO システムが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="3a2aa-116">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3a2aa-117">説明</span><span class="sxs-lookup"><span data-stu-id="3a2aa-117">Explanation</span></span>  
 <span data-ttu-id="3a2aa-118">ホスト側開始シングル サインオンは、SSO システムが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="3a2aa-118">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3a2aa-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3a2aa-119">User Action</span></span>  
 <span data-ttu-id="3a2aa-120">ホスト側開始シングル サインオンを構成するのにには、管理ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="3a2aa-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="3a2aa-121">これは、設定は、</span><span class="sxs-lookup"><span data-stu-id="3a2aa-121">This will set the</span></span>  
  
 <span data-ttu-id="3a2aa-122">グローバル情報の SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS フラグ。</span><span class="sxs-lookup"><span data-stu-id="3a2aa-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the global information.</span></span>