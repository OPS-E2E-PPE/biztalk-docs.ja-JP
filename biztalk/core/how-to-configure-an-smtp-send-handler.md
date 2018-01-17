---
title: "SMTP 送信ハンドラを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 2015-10-22
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send handlers, SMTP adapters
- SMTP adapters, send handlers
- configuring [SMTP adapters], send handlers
ms.assetid: b68a36ce-f0a5-4302-a405-bb154c935f47
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99dc71cf04d8a80b3a88630908a814957c83b8cb
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-configure-an-smtp-send-handler"></a><span data-ttu-id="9c7be-102">SMTP 送信ハンドラを構成する方法</span><span class="sxs-lookup"><span data-stu-id="9c7be-102">How to Configure an SMTP Send Handler</span></span>
<span data-ttu-id="9c7be-103">SMTP 送信ハンドラのプロパティは、BizTalk 管理コンソールで設定できます。</span><span class="sxs-lookup"><span data-stu-id="9c7be-103">You can set SMTP send handler properties in the BizTalk Administration console.</span></span> <span data-ttu-id="9c7be-104">個別の SMTP 送信ポートでプロパティが設定されていない場合は、これらの送信ハンドラのプロパティが送信ポートの構成値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c7be-104">These send handler properties are used as the send port configuration values if the properties are not set on the individual SMTP send port.</span></span>  
  
### <a name="to-change-global-variables-for-an-smtp-send-handler"></a><span data-ttu-id="9c7be-105">SMTP 送信ハンドラのグローバル変数を変更するには</span><span class="sxs-lookup"><span data-stu-id="9c7be-105">To change global variables for an SMTP send handler</span></span>  
  
1.  <span data-ttu-id="9c7be-106">BizTalk Server 管理コンソールで、展開[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="9c7be-106">In the BizTalk Server Administration Console, expand [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="9c7be-107">展開したアダプターの一覧でクリックして **SMTP**, 、右側のペインで、構成する送信ハンドラーを右クリックしをクリック **プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9c7be-107">In the expanded adapter list, click **SMTP**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9c7be-108">**アダプター ハンドラーのプロパティ**  ダイアログ ボックスの 、 **全般的な**  タブで、 **ホスト名** 一覧で、使用する送信ハンドラー、関連付けられているとする をクリックし、ホストを選択 **プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9c7be-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="9c7be-109">**SMTP トランスポートのプロパティ**  ダイアログ ボックスで、 **プロパティ**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="9c7be-109">In the **SMTP Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="9c7be-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9c7be-110">Use this</span></span>|<span data-ttu-id="9c7be-111">目的</span><span class="sxs-lookup"><span data-stu-id="9c7be-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9c7be-112">**SMTP サーバー名と TCP ポート**</span><span class="sxs-lookup"><span data-stu-id="9c7be-112">**SMTP server name and TCP port**</span></span>|**[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]**<br /><br /> <span data-ttu-id="9c7be-113">必須。</span><span class="sxs-lookup"><span data-stu-id="9c7be-113">Required.</span></span> <span data-ttu-id="9c7be-114">SMTP サーバー名とメッセージを送信するときに使用する (省略可能) の TCP ポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c7be-114">Enter the SMTP server  name and the TCP port number (optional) to use when sending messages.</span></span> <span data-ttu-id="9c7be-115">たとえば、次のように入力することができます。</span><span class="sxs-lookup"><span data-stu-id="9c7be-115">For example, you can enter:</span></span><br /><br /> <span data-ttu-id="9c7be-116">-mySMTPserver</span><span class="sxs-lookup"><span data-stu-id="9c7be-116">-   mySMTPserver</span></span><br /><span data-ttu-id="9c7be-117">-mySMTPserver.internet.com:2525</span><span class="sxs-lookup"><span data-stu-id="9c7be-117">-   mySMTPserver.internet.com:2525</span></span><br /><br /> <span data-ttu-id="9c7be-118">**以前のバージョンの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  (BizTalk Server 2013) を含むのみ、SMTP サーバー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c7be-118">**In previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** (including BizTalk Server 2013), enter only the SMTP server name.</span></span> <span data-ttu-id="9c7be-119">TCP ポート 25 では、ハード コードされます。</span><span class="sxs-lookup"><span data-stu-id="9c7be-119">TCP Port 25 is hard-coded.</span></span><br /><br /> <span data-ttu-id="9c7be-120">最大長: 256</span><span class="sxs-lookup"><span data-stu-id="9c7be-120">Maximum length: 256</span></span>|  
    |<span data-ttu-id="9c7be-121">**差出人 (電子メール アドレス)**</span><span class="sxs-lookup"><span data-stu-id="9c7be-121">**From (e-mail address)**</span></span>|<span data-ttu-id="9c7be-122">必須。</span><span class="sxs-lookup"><span data-stu-id="9c7be-122">Required.</span></span> <span data-ttu-id="9c7be-123">SMTP に配置する電子メール アドレスを入力 **から** ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="9c7be-123">Enter the e-mail address to put on the SMTP **From** header.</span></span><br /><br /> <span data-ttu-id="9c7be-124">最大長: 256</span><span class="sxs-lookup"><span data-stu-id="9c7be-124">Maximum length: 256</span></span>|  
    |<span data-ttu-id="9c7be-125">**認証の種類**</span><span class="sxs-lookup"><span data-stu-id="9c7be-125">**Authentication type**</span></span>|<span data-ttu-id="9c7be-126">SMTP サーバーで使用する認証の種類を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c7be-126">Enter the type of authentication to use with the SMTP server.</span></span><br /><br /> <span data-ttu-id="9c7be-127">オプション：</span><span class="sxs-lookup"><span data-stu-id="9c7be-127">Options:</span></span><br /><br /> <span data-ttu-id="9c7be-128">-   **[認証なし]**</span><span class="sxs-lookup"><span data-stu-id="9c7be-128">-   **No authentication**</span></span><br /><span data-ttu-id="9c7be-129">-   **基本認証**</span><span class="sxs-lookup"><span data-stu-id="9c7be-129">-   **Basic authentication**</span></span><br /><span data-ttu-id="9c7be-130">-   **プロセス アカウント (NTLM)**</span><span class="sxs-lookup"><span data-stu-id="9c7be-130">-   **Process account (NTLM)**</span></span><br /><br /> <span data-ttu-id="9c7be-131">既定値: プロセス アカウント (NTLM)</span><span class="sxs-lookup"><span data-stu-id="9c7be-131">Default value: Process account (NTLM)</span></span>|  
    |<span data-ttu-id="9c7be-132">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="9c7be-132">**User name**</span></span>|<span data-ttu-id="9c7be-133">SMTP サーバーで認証を使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c7be-133">Enter the user name to use for authentication with the SMTP server.</span></span><br /><br /> <span data-ttu-id="9c7be-134">場合、このプロパティが値を必要と **認証の種類** は **基本認証**します。</span><span class="sxs-lookup"><span data-stu-id="9c7be-134">This property requires a value if **Authentication type** is **Basic authentication**.</span></span><br /><br /> <span data-ttu-id="9c7be-135">最小長: 0</span><span class="sxs-lookup"><span data-stu-id="9c7be-135">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="9c7be-136">最大長: 256</span><span class="sxs-lookup"><span data-stu-id="9c7be-136">Maximum length: 256</span></span>|  
    |<span data-ttu-id="9c7be-137">**パスワード**</span><span class="sxs-lookup"><span data-stu-id="9c7be-137">**Password**</span></span>|<span data-ttu-id="9c7be-138">SMTP サーバーで認証を使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="9c7be-138">Enter the password to use for authentication with the SMTP server.</span></span><br /><br /> <span data-ttu-id="9c7be-139">場合、このプロパティが値を必要と **認証の種類** は **基本認証**します。</span><span class="sxs-lookup"><span data-stu-id="9c7be-139">This property requires a value if **Authentication type** is **Basic authentication**.</span></span><br /><br /> <span data-ttu-id="9c7be-140">最小長: 0</span><span class="sxs-lookup"><span data-stu-id="9c7be-140">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="9c7be-141">最大長: 256</span><span class="sxs-lookup"><span data-stu-id="9c7be-141">Maximum length: 256</span></span>|  
  
5.  <span data-ttu-id="9c7be-142">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c7be-142">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7be-143">参照</span><span class="sxs-lookup"><span data-stu-id="9c7be-143">See Also</span></span>  
 [<span data-ttu-id="9c7be-144">SMTP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="9c7be-144">Configuring the SMTP Adapter</span></span>](../core/configuring-the-smtp-adapter.md)