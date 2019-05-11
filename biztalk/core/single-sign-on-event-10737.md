---
title: シングル サインオン:イベント 10737 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2102930b-8b1f-4d48-a14d-e8884dc7f9aa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 522eac1a2a70b1518f35c58d82ede99d6a402af0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270935"
---
# <a name="single-sign-on-event-10737"></a><span data-ttu-id="8d0eb-102">シングル サインオン:イベント 10737</span><span class="sxs-lookup"><span data-stu-id="8d0eb-102">Single Sign-On: Event 10737</span></span>
## <a name="details"></a><span data-ttu-id="8d0eb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8d0eb-103">Details</span></span>  

|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8d0eb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8d0eb-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="8d0eb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8d0eb-105">Enterprise Single Sign-On</span></span>                                                                                                |
| <span data-ttu-id="8d0eb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8d0eb-106">Product Version</span></span> |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="8d0eb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8d0eb-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="8d0eb-108">10737</span><span class="sxs-lookup"><span data-stu-id="8d0eb-108">10737</span></span>                                                                                                          |
|  <span data-ttu-id="8d0eb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8d0eb-109">Event Source</span></span>   |                                                                                                         <span data-ttu-id="8d0eb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8d0eb-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="8d0eb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8d0eb-111">Component</span></span>    |                                                                                                          <span data-ttu-id="8d0eb-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="8d0eb-112">N\A</span></span>                                                                                                           |
|  <span data-ttu-id="8d0eb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8d0eb-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="8d0eb-114">SSO_WARN_PS_SET_EXTERNAL_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="8d0eb-114">SSO_WARN_PS_SET_EXTERNAL_PASSWORD</span></span>                                                                                            |
|  <span data-ttu-id="8d0eb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8d0eb-115">Message Text</span></span>   | <span data-ttu-id="8d0eb-116">SSO database.%r 内の外部パスワードを更新できませんでした。</span><span class="sxs-lookup"><span data-stu-id="8d0eb-116">Failed to update the external password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="8d0eb-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8d0eb-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="8d0eb-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="8d0eb-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="8d0eb-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="8d0eb-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="8d0eb-120">外部アカウント: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="8d0eb-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="8d0eb-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="8d0eb-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="8d0eb-122">説明</span><span class="sxs-lookup"><span data-stu-id="8d0eb-122">Explanation</span></span>  
 <span data-ttu-id="8d0eb-123">この警告イベントは、SSO が SSO データベース内の外部パスワードの更新に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="8d0eb-123">This Warning event indicates that SSO failed to update the external password in the SSO database.</span></span> <span data-ttu-id="8d0eb-124">さまざまな警告メッセージに示されているエラーの原因が考えられます場合によっては、この警告は、構成の問題を示す可能性があります。 またはマッピングが削除されているパスワードの変更プロセスの中にします。</span><span class="sxs-lookup"><span data-stu-id="8d0eb-124">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8d0eb-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8d0eb-125">User Action</span></span>  
 <span data-ttu-id="8d0eb-126">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8d0eb-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="8d0eb-127">パスワードの変更を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="8d0eb-127">Retry the password change.</span></span>  

- <span data-ttu-id="8d0eb-128">追加の試行も失敗する場合は、UI またはコマンド ライン ツールを使用して手動でパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="8d0eb-128">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  

  <span data-ttu-id="8d0eb-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d0eb-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="8d0eb-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="8d0eb-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
