---
title: 'シングル サインオン: イベント 10676 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec0e86fb-921d-4505-b458-51b565123ea7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63228e82546e100c81bf01c301d7d9507f147671
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991931"
---
# <a name="single-sign-on-event-10676"></a><span data-ttu-id="0d0e9-102">シングル サインオン: イベント 10676</span><span class="sxs-lookup"><span data-stu-id="0d0e9-102">Single Sign-On: Event 10676</span></span>
## <a name="details"></a><span data-ttu-id="0d0e9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0d0e9-103">Details</span></span>  

|                 |                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0d0e9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0d0e9-104">Product Name</span></span>   |                                                                                             <span data-ttu-id="0d0e9-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0d0e9-105">Enterprise Single Sign-On</span></span>                                                                                             |
| <span data-ttu-id="0d0e9-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0d0e9-106">Product Version</span></span> |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    <span data-ttu-id="0d0e9-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0d0e9-107">Event ID</span></span>     |                                                                                                       <span data-ttu-id="0d0e9-108">10676</span><span class="sxs-lookup"><span data-stu-id="0d0e9-108">10676</span></span>                                                                                                       |
|  <span data-ttu-id="0d0e9-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0d0e9-109">Event Source</span></span>   |                                                                                                      <span data-ttu-id="0d0e9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0d0e9-110">ENTSSO</span></span>                                                                                                       |
|    <span data-ttu-id="0d0e9-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0d0e9-111">Component</span></span>    |                                                                                                        <span data-ttu-id="0d0e9-112">N\A</span><span class="sxs-lookup"><span data-stu-id="0d0e9-112">N\A</span></span>                                                                                                        |
|  <span data-ttu-id="0d0e9-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0d0e9-113">Symbolic Name</span></span>  |                                                                                          <span data-ttu-id="0d0e9-114">SSO_ERROR_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="0d0e9-114">SSO_ERROR_REQUIRE_OLD_PASSWORD</span></span>                                                                                           |
|  <span data-ttu-id="0d0e9-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0d0e9-115">Message Text</span></span>   | <span data-ttu-id="0d0e9-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="0d0e9-116">External password change.</span></span> <span data-ttu-id="0d0e9-117">外部アカウントのパスワードを変更するとき、アダプターで古いパスワードを指定する必要があります。%r</span><span class="sxs-lookup"><span data-stu-id="0d0e9-117">When changing the password for an external account the adapter must supply the old password.%r</span></span><br /><br /> <span data-ttu-id="0d0e9-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0d0e9-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0d0e9-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="0d0e9-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="0d0e9-120">外部アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="0d0e9-120">External Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="0d0e9-121">説明</span><span class="sxs-lookup"><span data-stu-id="0d0e9-121">Explanation</span></span>  
 <span data-ttu-id="0d0e9-122">このエラー イベントは、パスワード同期アダプターは外部システムの古いパスワードを必要とするように構成されていましたが、古いパスワードが指定されなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0d0e9-122">This Error event indicates that the password sync adapter was configured to expect an old password from the external system, but an old password was not provided.</span></span> <span data-ttu-id="0d0e9-123">外部システム (外部パスワード同期アダプター) が意図したように構成されていない、または動作していないか、またはパスワード同期アダプターが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="0d0e9-123">Either the external system (the external password sync adapter) is not configured or working as expected or the password sync adapter is incorrectly configured.</span></span> <span data-ttu-id="0d0e9-124">このエラーからはエラー コード シンボリック名 ENTSSO_E_REQUIRE_OLD_PASSWORD も返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d0e9-124">This error may also return error code symbolic name ENTSSO_E_REQUIRE_OLD_PASSWORD.</span></span>  

## <a name="user-action"></a><span data-ttu-id="0d0e9-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0d0e9-125">User Action</span></span>  
 <span data-ttu-id="0d0e9-126">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0d0e9-126">To resolve this error, do the following:</span></span>  

-   <span data-ttu-id="0d0e9-127">SSO 管理ツールを使用して、ユーザー構成可能なプロパティを設定する**古いパスワードの確認**パスワード同期アダプターのオプションのプロパティ タブ。このプロパティは、アダプターを作成するときにコマンド ライン ツール (ssops.exe) と `verifyOldPassword` という名前のフラグを使用して、およびパスワード同期アダプター ウィザードを使用して新しいパスワード同期アダプターを作成するときに、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0d0e9-127">Use the SSO administration tools to set the user configurable property **Verify Old Password** on the Password Sync Adapter Options properties tab. This property can also be set when creating adapters via the command line tools (ssops.exe) with the flag name `verifyOldPassword` and also when creating a new password sync adapter using the Password Sync Adapter wizard.</span></span>  

## <a name="more-info"></a><span data-ttu-id="0d0e9-128">詳細</span><span class="sxs-lookup"><span data-stu-id="0d0e9-128">More info</span></span>

- [<span data-ttu-id="0d0e9-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="0d0e9-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="0d0e9-130">**パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0d0e9-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
