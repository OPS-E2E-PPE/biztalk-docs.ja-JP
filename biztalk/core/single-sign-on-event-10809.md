---
title: シングル サインオン:イベント 10809 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dc0f1b98ed1b9b3e414888b01f2693a9f1786f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65293003"
---
# <a name="single-sign-on-event-10809"></a><span data-ttu-id="4779b-102">シングル サインオン:イベント 10809</span><span class="sxs-lookup"><span data-stu-id="4779b-102">Single Sign-On: Event 10809</span></span>
## <a name="details"></a><span data-ttu-id="4779b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4779b-103">Details</span></span>  
  
|                 |                                                                   |
|-----------------|-------------------------------------------------------------------|
|  <span data-ttu-id="4779b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4779b-104">Product Name</span></span>   |                     <span data-ttu-id="4779b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4779b-105">Enterprise Single Sign-On</span></span>                     |
| <span data-ttu-id="4779b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4779b-106">Product Version</span></span> |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]     |
|    <span data-ttu-id="4779b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4779b-107">Event ID</span></span>     |                               <span data-ttu-id="4779b-108">10809</span><span class="sxs-lookup"><span data-stu-id="4779b-108">10809</span></span>                               |
|  <span data-ttu-id="4779b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4779b-109">Event Source</span></span>   |                              <span data-ttu-id="4779b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4779b-110">ENTSSO</span></span>                               |
|    <span data-ttu-id="4779b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4779b-111">Component</span></span>    |                                <span data-ttu-id="4779b-112">なし</span><span class="sxs-lookup"><span data-stu-id="4779b-112">N/A</span></span>                                |
|  <span data-ttu-id="4779b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4779b-113">Symbolic Name</span></span>  |                  <span data-ttu-id="4779b-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="4779b-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span></span>                   |
|  <span data-ttu-id="4779b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4779b-115">Message Text</span></span>   | <span data-ttu-id="4779b-116">ホスト側開始シングル サインオンは、アプリケーションが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="4779b-116">The application is not enabled for Host Initiated Single Sign-On.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4779b-117">説明</span><span class="sxs-lookup"><span data-stu-id="4779b-117">Explanation</span></span>  
 <span data-ttu-id="4779b-118">ホスト側開始シングル サインオンは、アプリケーションが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="4779b-118">The application is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4779b-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4779b-119">User Action</span></span>  
 <span data-ttu-id="4779b-120">ホスト側開始シングル サインオンを構成するのにには、管理ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="4779b-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="4779b-121">これは、設定は、</span><span class="sxs-lookup"><span data-stu-id="4779b-121">This will set the</span></span>  
  
 <span data-ttu-id="4779b-122">アプリケーションの SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS フラグ。</span><span class="sxs-lookup"><span data-stu-id="4779b-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the application.</span></span>