---
title: シングル サインオン:イベント 10676 |Microsoft Docs
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
ms.openlocfilehash: d1779d8f30d4e82d9c63dacc503cbd9dfab555a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397476"
---
# <a name="single-sign-on-event-10676"></a><span data-ttu-id="6d0f2-102">シングル サインオン:イベント 10676</span><span class="sxs-lookup"><span data-stu-id="6d0f2-102">Single Sign-On: Event 10676</span></span>
## <a name="details"></a><span data-ttu-id="6d0f2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6d0f2-103">Details</span></span>  

|                 |                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6d0f2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6d0f2-104">Product Name</span></span>   |                                                                                             <span data-ttu-id="6d0f2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6d0f2-105">Enterprise Single Sign-On</span></span>                                                                                             |
| <span data-ttu-id="6d0f2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6d0f2-106">Product Version</span></span> |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    <span data-ttu-id="6d0f2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6d0f2-107">Event ID</span></span>     |                                                                                                       <span data-ttu-id="6d0f2-108">10676</span><span class="sxs-lookup"><span data-stu-id="6d0f2-108">10676</span></span>                                                                                                       |
|  <span data-ttu-id="6d0f2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6d0f2-109">Event Source</span></span>   |                                                                                                      <span data-ttu-id="6d0f2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6d0f2-110">ENTSSO</span></span>                                                                                                       |
|    <span data-ttu-id="6d0f2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6d0f2-111">Component</span></span>    |                                                                                                        <span data-ttu-id="6d0f2-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="6d0f2-112">N\A</span></span>                                                                                                        |
|  <span data-ttu-id="6d0f2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6d0f2-113">Symbolic Name</span></span>  |                                                                                          <span data-ttu-id="6d0f2-114">SSO_ERROR_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="6d0f2-114">SSO_ERROR_REQUIRE_OLD_PASSWORD</span></span>                                                                                           |
|  <span data-ttu-id="6d0f2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6d0f2-115">Message Text</span></span>   | <span data-ttu-id="6d0f2-116">外部パスワード変更。</span><span class="sxs-lookup"><span data-stu-id="6d0f2-116">External password change.</span></span> <span data-ttu-id="6d0f2-117">外部アカウントのパスワードを変更するときに、アダプターが古い password.%r を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d0f2-117">When changing the password for an external account the adapter must supply the old password.%r</span></span><br /><br /> <span data-ttu-id="6d0f2-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6d0f2-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="6d0f2-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="6d0f2-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="6d0f2-120">外部アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="6d0f2-120">External Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="6d0f2-121">説明</span><span class="sxs-lookup"><span data-stu-id="6d0f2-121">Explanation</span></span>  
 <span data-ttu-id="6d0f2-122">このエラー イベントは、古いパスワードが指定されていませんが、パスワード同期アダプターは、外部のシステムからの古いパスワードが構成されたを示します。</span><span class="sxs-lookup"><span data-stu-id="6d0f2-122">This Error event indicates that the password sync adapter was configured to expect an old password from the external system, but an old password was not provided.</span></span> <span data-ttu-id="6d0f2-123">外部システム (外部パスワード同期アダプター) が構成されていないか、正常に動作またはパスワード同期アダプターが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="6d0f2-123">Either the external system (the external password sync adapter) is not configured or working as expected or the password sync adapter is incorrectly configured.</span></span> <span data-ttu-id="6d0f2-124">このエラーは、エラー コード シンボリック名 ENTSSO_E_REQUIRE_OLD_PASSWORD を返すも可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d0f2-124">This error may also return error code symbolic name ENTSSO_E_REQUIRE_OLD_PASSWORD.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6d0f2-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6d0f2-125">User Action</span></span>  
 <span data-ttu-id="6d0f2-126">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d0f2-126">To resolve this error, do the following:</span></span>  

-   <span data-ttu-id="6d0f2-127">SSO 管理ツールを使用して、ユーザー構成可能なプロパティを設定する**古いパスワードの確認**パスワード同期アダプターのオプションのプロパティ タブ。このプロパティは、フラグの名前を持つツール (ssops.exe) のコマンドラインを使用してアダプターを作成するときにも設定できます`verifyOldPassword`と新しいパスワードを作成する同期も、パスワード同期アダプター ウィザードを使用してアダプターとします。</span><span class="sxs-lookup"><span data-stu-id="6d0f2-127">Use the SSO administration tools to set the user configurable property **Verify Old Password** on the Password Sync Adapter Options properties tab. This property can also be set when creating adapters via the command line tools (ssops.exe) with the flag name `verifyOldPassword` and also when creating a new password sync adapter using the Password Sync Adapter wizard.</span></span>  

## <a name="more-info"></a><span data-ttu-id="6d0f2-128">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6d0f2-128">More info</span></span>

- [<span data-ttu-id="6d0f2-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="6d0f2-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="6d0f2-130">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6d0f2-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
