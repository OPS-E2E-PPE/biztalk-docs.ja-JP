---
title: "PeopleSoft トランスポートのプロパティを設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting transport properties
- transport properties, setting
ms.assetid: 44b5f015-59f1-43a3-9673-a5ba40266843
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ecfd221d28312e84dcbaf7d8c83abc4f5191f54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-peoplesoft-transport-properties"></a><span data-ttu-id="19087-102">PeopleSoft トランスポート プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="19087-102">Setting PeopleSoft Transport Properties</span></span>
<span data-ttu-id="19087-103">PeopleSoft トランスポートのプロパティは、設計時および実行時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="19087-103">The PeopleSoft transport properties are used for design and run time.</span></span> <span data-ttu-id="19087-104">**トランスポートのプロパティ**ダイアログ ボックスで、パラメーターを設定する接続と資格情報を特定サーバーのシステムおよびアクセスしようとしているオブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="19087-104">In the **Transport Properties** dialog box, you set the connection and credential parameters specific to the server system and the objects you are trying to access.</span></span>  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="19087-105">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="19087-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="19087-106">[アダプターに必要なプロパティ] を展開し、PeopleSoft サーバーへの接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="19087-106">Expand the Adapter Required Properties and fill in all required information for connection to the PeopleSoft server.</span></span>  
  
     <span data-ttu-id="19087-107">Microsoft BizTalk Adapter for PeopleSoft Enterprise を PeopleSoft Enterprise に接続するには、構成パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19087-107">You must set configuration parameters to connect Microsoft BizTalk Adapter for PeopleSoft Enterprise to PeopleSoft Enterprise.</span></span> <span data-ttu-id="19087-108">このデータは、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="19087-108">This data is case sensitive.</span></span>  
  
    |<span data-ttu-id="19087-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19087-109">Parameter</span></span>|<span data-ttu-id="19087-110">Description</span><span class="sxs-lookup"><span data-stu-id="19087-110">Description</span></span>|  
    |---------------|-----------------|  
    |`Application Server Path`|<span data-ttu-id="19087-111">PeopleSoft Application Server が動作して受信を待ち受けているコンピューターおよびポートを表す文字列。</span><span class="sxs-lookup"><span data-stu-id="19087-111">A string representing the computer and port on which the PeopleSoft Application Server is running and listening.</span></span> <span data-ttu-id="19087-112">PeopleSoft 8 Application への URL パスの構文は//< computer_name >:\<ポート >。</span><span class="sxs-lookup"><span data-stu-id="19087-112">The syntax of the URL path to the PeopleSoft 8 Application is //<computer_name>:\<port>.</span></span> <span data-ttu-id="19087-113">PeopleSoft 管理者に問い合わせて、\<ポート > 値。</span><span class="sxs-lookup"><span data-stu-id="19087-113">Ask your PeopleSoft administrator for the \<port> value.</span></span> <span data-ttu-id="19087-114">\<ポート > 値は、JOLT プロトコル リスナー ポート、App Server ポートではありません。</span><span class="sxs-lookup"><span data-stu-id="19087-114">The \<port> value is the JOLT protocol listener port, not the App Server port.</span></span> <span data-ttu-id="19087-115">既定の JOLT ポートは 9000 です。</span><span class="sxs-lookup"><span data-stu-id="19087-115">The default JOLT port is 9000.</span></span>|  
    |`JAVA_HOME`|<span data-ttu-id="19087-116">たとえば、JDK インストールを指すように JAVA_HOME 変数を設定します。 **C:\j2sdk1.4.2_08**です。</span><span class="sxs-lookup"><span data-stu-id="19087-116">Set the JAVA_HOME variable to point to your JDK installation, for example: **C:\j2sdk1.4.2_08**.</span></span>|  
    |`Password`|<span data-ttu-id="19087-117">選択しなかった場合**SSO を使用する**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19087-117">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="19087-118">PeopleSoft システムへのログオンに使用するユーザーのパスワードを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="19087-118">A string representing the user's password for logon to a PeopleSoft system.</span></span> <span data-ttu-id="19087-119">文字は表示されませんが、アスタリスク (*) で表されます。</span><span class="sxs-lookup"><span data-stu-id="19087-119">The characters do not appear but are represented by asterisks (*).</span></span>|  
    |`PeopleSoft 8.x Jar Files`|<span data-ttu-id="19087-120">コンポーネント インターフェイス (PeopleSoft 8 のみ) を使用するには、PeopleSoft Component Interface の jar ファイルが含まれるように CLASSPATH を更新する必要があります</span><span class="sxs-lookup"><span data-stu-id="19087-120">To use Ccmponent interfaces (PeopleSoft 8 only) you must update your CLASSPATH to include the PeopleSoft Component Interface jar file.</span></span> <span data-ttu-id="19087-121">例: **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**です。</span><span class="sxs-lookup"><span data-stu-id="19087-121">For example: **<PeopleSoft_Home>\web\PSJOA\psjoa.jar**.</span></span>|  
    |`User Name`|<span data-ttu-id="19087-122">選択しなかった場合**SSO を使用する**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19087-122">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="19087-123">PeopleSoft システムへのログオンに必要なユーザー名を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="19087-123">A string representing a user name required for logon to a PeopleSoft system.</span></span>|  
  
2.  <span data-ttu-id="19087-124">入力、**追加パラメーター**日付がキーとして使用するときの値とは別の形式です。</span><span class="sxs-lookup"><span data-stu-id="19087-124">Enter an **Additional parameters** value when a date is used as a key; it has a different format.</span></span> <span data-ttu-id="19087-125">既定の形式は YYYY-MM-DD です。</span><span class="sxs-lookup"><span data-stu-id="19087-125">YYYY-MM-DD is the default format.</span></span>  
  
3.  <span data-ttu-id="19087-126">入力、**同時実行制御**で呼び出し、たとえば 200 の数を表す値**Max Concurrent Calls**必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="19087-126">Enter a **Concurrency control** value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="19087-127">**Max Concurrent Calls**パラメーターは、バック エンド サーバーがデータの量を処理できない場合に、オーバー ロードの保護をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="19087-127">The **Max Concurrent Calls** parameter activates an overload protection if the back-end server cannot process the amount of data.</span></span> <span data-ttu-id="19087-128">同時呼び出しとは、アダプターがまだ返信を受信していない要求のことです。</span><span class="sxs-lookup"><span data-stu-id="19087-128">A concurrent call is a request for which the adapter does not yet have a reply.</span></span> <span data-ttu-id="19087-129">設定**Max Concurrent Calls**場合、スループットがバックエンドの処理能力を超えています。</span><span class="sxs-lookup"><span data-stu-id="19087-129">Set **Max Concurrent Calls** in instances where the throughput exceeds back-end processing capabilities.</span></span>  
  
     <span data-ttu-id="19087-130">このフィールドの既定値は -1 です。保護は発生しません。</span><span class="sxs-lookup"><span data-stu-id="19087-130">The default value for this field is -1, meaning no protection occurs.</span></span>  
  
     <span data-ttu-id="19087-131">BizTalk Server が送信アダプターに要求を送信し、同時実行の数が呼び出しまたはに設定された値を超えて 場合**Max Concurrent Calls**、同時呼び出しの数まで、要求を保存送信スレッド設定された値以下に低下します。</span><span class="sxs-lookup"><span data-stu-id="19087-131">If BizTalk Server submits a request to the Transmit adapter, and the number of concurrent calls equals or exceeds the value set for **Max Concurrent Calls**, the thread submitting the request is saved until the concurrent calls number decreases to below the set value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19087-132">参照</span><span class="sxs-lookup"><span data-stu-id="19087-132">See Also</span></span>  
 [<span data-ttu-id="19087-133">PeopleSoft 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="19087-133">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)