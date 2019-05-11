---
title: シングル サインオン:イベント 11049 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 031ec1a6-4b2b-46b2-9dbb-5525d758651f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a41631744b25149135de4e3c65b5ccd436dcd0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400991"
---
# <a name="single-sign-on-event-11049"></a><span data-ttu-id="34169-102">シングル サインオン:イベント 11049</span><span class="sxs-lookup"><span data-stu-id="34169-102">Single Sign-On: Event 11049</span></span>
## <a name="details"></a><span data-ttu-id="34169-103">詳細</span><span class="sxs-lookup"><span data-stu-id="34169-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="34169-104">製品名</span><span class="sxs-lookup"><span data-stu-id="34169-104">Product Name</span></span>   |                   <span data-ttu-id="34169-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="34169-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="34169-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="34169-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="34169-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="34169-107">Event ID</span></span>     |                             <span data-ttu-id="34169-108">11049</span><span class="sxs-lookup"><span data-stu-id="34169-108">11049</span></span>                              |
|  <span data-ttu-id="34169-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="34169-109">Event Source</span></span>   |                             <span data-ttu-id="34169-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="34169-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="34169-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="34169-111">Component</span></span>    |                              <span data-ttu-id="34169-112">なし</span><span class="sxs-lookup"><span data-stu-id="34169-112">N/A</span></span>                               |
|  <span data-ttu-id="34169-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="34169-113">Symbolic Name</span></span>  |                      <span data-ttu-id="34169-114">SSO_ERROR_DTC_FAILED</span><span class="sxs-lookup"><span data-stu-id="34169-114">SSO_ERROR_DTC_FAILED</span></span>                      |
|  <span data-ttu-id="34169-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="34169-115">Message Text</span></span>   | <span data-ttu-id="34169-116">MSDTC を取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="34169-116">Could not get MSDTC.</span></span> <span data-ttu-id="34169-117">SSO を正しく機能させるには MSDTC が必要です。</span><span class="sxs-lookup"><span data-stu-id="34169-117">SSO requires MSDTC for correct operation.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="34169-118">説明</span><span class="sxs-lookup"><span data-stu-id="34169-118">Explanation</span></span>  
 <span data-ttu-id="34169-119">ENTSSO システムが、Microsoft 分散トランザクション コーディネーター (MSDTC) に接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="34169-119">The ENTSSO system could not connect to the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="34169-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="34169-120">User Action</span></span>  
 <span data-ttu-id="34169-121">MSDTC が現在動作しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="34169-121">Check to see if MSDTC is currently operational.</span></span>  
  
 <span data-ttu-id="34169-122">MSDTC の問題に関するヘルプは、次を参照してください。 [MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)します。</span><span class="sxs-lookup"><span data-stu-id="34169-122">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>