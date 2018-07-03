---
title: Office 365 Outlook メール アダプターを使用して、|Microsoft Docs
description: Office 365 Outlook のアダプターを BizTalk server で電子メール、予定表、連絡先などを使用してメッセージを送受信することの概要
ms.custom: ''
ms.date: 06/19/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: ribarua
manager: dougeby
ms.openlocfilehash: 2002ab6859a71a930ef9166f9b3a5a072ba77948
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946237"
---
# <a name="office-365-outlook-adapters-in-biztalk"></a><span data-ttu-id="7c969-103">BizTalk での office 365 Outlook のアダプター</span><span class="sxs-lookup"><span data-stu-id="7c969-103">Office 365 Outlook adapters in BizTalk</span></span>

## <a name="overview"></a><span data-ttu-id="7c969-104">概要</span><span class="sxs-lookup"><span data-stu-id="7c969-104">Overview</span></span>
<span data-ttu-id="7c969-105">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]機能パック 3**、BizTalk Server と Office 365 Outlook の機能の間でメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="7c969-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 3**, you can send and receive messages between BizTalk Server and Office 365 Outlook features.</span></span> <span data-ttu-id="7c969-106">機能パック 3 では、次のアダプターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c969-106">The following adapters are included in Feature Pack 3:</span></span>

- [<span data-ttu-id="7c969-107">Office 365 Outlook メール アダプター</span><span class="sxs-lookup"><span data-stu-id="7c969-107">Office 365 Outlook Email adapter</span></span>](office365-mail-adapter.md)
- [<span data-ttu-id="7c969-108">Office 365 Outlook の予定表のアダプター</span><span class="sxs-lookup"><span data-stu-id="7c969-108">Office 365 Outlook Calendar adapter</span></span>](office365-calendar-adapter.md)
- [<span data-ttu-id="7c969-109">Office 365 Outlook の連絡先のアダプター</span><span class="sxs-lookup"><span data-stu-id="7c969-109">Office 365 Outlook Contact adapter</span></span>](office365-contact-adapter.md)

## <a name="prerequisites"></a><span data-ttu-id="7c969-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="7c969-110">Prerequisites</span></span>

* <span data-ttu-id="7c969-111">[Office 365 アカウント](https://outlook.office365.com)</span><span class="sxs-lookup"><span data-stu-id="7c969-111">Have an [Office 365 account](https://outlook.office365.com)</span></span>
* <span data-ttu-id="7c969-112">インストール[Feature Pack 3](https://aka.ms/bts2016fp3) BizTalk Server で</span><span class="sxs-lookup"><span data-stu-id="7c969-112">Install [Feature Pack 3](https://aka.ms/bts2016fp3) on your BizTalk Server</span></span>
* <span data-ttu-id="7c969-113">SSO 管理者グループのメンバーであるアカウントを使用して、</span><span class="sxs-lookup"><span data-stu-id="7c969-113">Use an account that is a member of the SSO Administrators group</span></span>

## <a name="tms-overview"></a><span data-ttu-id="7c969-114">TMS の概要</span><span class="sxs-lookup"><span data-stu-id="7c969-114">TMS overview</span></span>

<span data-ttu-id="7c969-115">BizTalk Server TMS は、BizTalk で使用される Office 365 の OAuth トークンを更新するサービスです。</span><span class="sxs-lookup"><span data-stu-id="7c969-115">BizTalk Server TMS is a service that refreshes the Office 365 OAuth tokens used by BizTalk.</span></span> <span data-ttu-id="7c969-116">トークンが有効なが常にあることを確認、定期的にトークンを更新します。</span><span class="sxs-lookup"><span data-stu-id="7c969-116">It refreshes these tokens periodically, ensuring that the tokens always remain valid.</span></span> <span data-ttu-id="7c969-117">エンタープライズ シングル サインオン サービス (ENT SSO) に依存しているし、マスター シークレット サーバーをホストするコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c969-117">It has a dependency on Enterprise Single Sign On service (ENT SSO), and must be installed on a computer that hosts the master secret server.</span></span> 

## <a name="install-biztalk-server-tms"></a><span data-ttu-id="7c969-118">BizTalk Server TMS をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7c969-118">Install BizTalk Server TMS</span></span>

1. <span data-ttu-id="7c969-119">インストール[Feature Pack 3](https://aka.ms/bts2016fp3)します。</span><span class="sxs-lookup"><span data-stu-id="7c969-119">Install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>
2. <span data-ttu-id="7c969-120">`\Program Files (x86)\Microsoft BizTalk Server <your version>`BizTalkTMS.msi を実行します。</span><span class="sxs-lookup"><span data-stu-id="7c969-120">In `\Program Files (x86)\Microsoft BizTalk Server <your version>`, run BizTalkTMS.msi.</span></span>
3. <span data-ttu-id="7c969-121">ユーザー名と SSO 管理者グループのメンバーであるユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7c969-121">Enter the username and password of a user that's a member of the SSO Administrators group.</span></span> 

![BizTalk Server TMS のセットアップ](../core/media/BizTalk-TMS.png)

## <a name="sign-in-to-office-365"></a><span data-ttu-id="7c969-123">Office 365 にサインイン</span><span class="sxs-lookup"><span data-stu-id="7c969-123">Sign-in to Office 365</span></span>

<span data-ttu-id="7c969-124">作成する際、[送信ポート](how-to-create-a-send-port2.md)または[受信場所](how-to-create-a-receive-location.md)BizTalk 管理コンソールで実行できます**でサインインしています.** を Office 365 アカウント。</span><span class="sxs-lookup"><span data-stu-id="7c969-124">When you're creating a [send port](how-to-create-a-send-port2.md) or [receive location](how-to-create-a-receive-location.md) in BizTalk Administration, you can **Sign-in...** to your Office 365 account:</span></span>

  ![Office 365 のサインイン](../core/media/office365-signin.png)

<span data-ttu-id="7c969-126">Office 365 の資格情報を入力し、アクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c969-126">You enter the Office 365 credentials, and confirm permissions.</span></span> <span data-ttu-id="7c969-127">これらの資格情報は、BizTalk には、接続を承認し、Office 365 アカウントへのアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7c969-127">These credentials authorize BizTalk to connect to, and access the Office 365 account.</span></span> <span data-ttu-id="7c969-128">次の例では、Office 365 Outlook の予定表のアクセス許可が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c969-128">In the following example, you see the permissions for Office 365 Outlook Calendar:</span></span>

  ![Office 365 カレンダーのアクセス許可](../core/media/office365-calendar-permissions.png)

## <a name="get-started"></a><span data-ttu-id="7c969-130">作業開始</span><span class="sxs-lookup"><span data-stu-id="7c969-130">Get started</span></span>
<span data-ttu-id="7c969-131">BizTalk Server TMS をインストールした後は、成果物を作成し、アダプターの使用を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="7c969-131">After BizTalk Server TMS is installed, you're ready to create the artifacts, and start using the adapters:</span></span>

- [<span data-ttu-id="7c969-132">Office 365 Outlook メール アダプター</span><span class="sxs-lookup"><span data-stu-id="7c969-132">Office 365 Outlook Email adapter</span></span>](./office365-mail-adapter.md)
- [<span data-ttu-id="7c969-133">Office 365 Outlook の予定表のアダプター</span><span class="sxs-lookup"><span data-stu-id="7c969-133">Office 365 Outlook Calendar adapter</span></span>](./office365-calendar-adapter.md)
- [<span data-ttu-id="7c969-134">Office 365 Outlook の連絡先のアダプター</span><span class="sxs-lookup"><span data-stu-id="7c969-134">Office 365 Outlook Contact adapter</span></span>](./office365-contact-adapter.md)
