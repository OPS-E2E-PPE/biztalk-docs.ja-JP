---
title: シングル サインオン:イベント 10810 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a2d22ad-d5a8-4d32-af1d-8fa7237fd7ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1191e54baaeb4caf16dd72f841b3ec9cf666123
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396162"
---
# <a name="single-sign-on-event-10810"></a><span data-ttu-id="548eb-102">シングル サインオン:イベント 10810</span><span class="sxs-lookup"><span data-stu-id="548eb-102">Single Sign-On: Event 10810</span></span>
## <a name="details"></a><span data-ttu-id="548eb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="548eb-103">Details</span></span>  
  
|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  <span data-ttu-id="548eb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="548eb-104">Product Name</span></span>   |                            <span data-ttu-id="548eb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="548eb-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="548eb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="548eb-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="548eb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="548eb-107">Event ID</span></span>     |                                      <span data-ttu-id="548eb-108">10810</span><span class="sxs-lookup"><span data-stu-id="548eb-108">10810</span></span>                                       |
|  <span data-ttu-id="548eb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="548eb-109">Event Source</span></span>   |                                      <span data-ttu-id="548eb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="548eb-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="548eb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="548eb-111">Component</span></span>    |                                       <span data-ttu-id="548eb-112">なし</span><span class="sxs-lookup"><span data-stu-id="548eb-112">N/A</span></span>                                        |
|  <span data-ttu-id="548eb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="548eb-113">Symbolic Name</span></span>  |                        <span data-ttu-id="548eb-114">ENTSSO_E_HISSO_INVALID_CREDENTIALS</span><span class="sxs-lookup"><span data-stu-id="548eb-114">ENTSSO_E_HISSO_INVALID_CREDENTIALS</span></span>                        |
|  <span data-ttu-id="548eb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="548eb-115">Message Text</span></span>   | <span data-ttu-id="548eb-116">指定された資格情報が無効か、SSO データベースと一致しません。</span><span class="sxs-lookup"><span data-stu-id="548eb-116">The specified credentials are invalid or do not match those in the SSO database.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="548eb-117">説明</span><span class="sxs-lookup"><span data-stu-id="548eb-117">Explanation</span></span>  
 <span data-ttu-id="548eb-118">指定された資格情報が無効か、SSO データベースと一致しません。</span><span class="sxs-lookup"><span data-stu-id="548eb-118">The specified credentials are invalid or do not match those in the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="548eb-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="548eb-119">User Action</span></span>  
 <span data-ttu-id="548eb-120">外部システムからの情報に一致するように、SSO データベース内の情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="548eb-120">Set the information in the SSO database to match the information from the external system.</span></span>