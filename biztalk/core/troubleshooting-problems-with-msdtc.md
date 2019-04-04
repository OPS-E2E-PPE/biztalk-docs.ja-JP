---
title: MSDTC に関する問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f39cde52-da8f-4cc1-bdc5-e4b828891a79
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95776b7b03cc1b6bca08622d126153cb22efc317
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987723"
---
# <a name="troubleshooting-problems-with-msdtc"></a><span data-ttu-id="bdec7-102">MSDTC を使用した問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bdec7-102">Troubleshooting Problems with MSDTC</span></span>
<span data-ttu-id="bdec7-103">多くの BizTalk Server ランタイム操作では、トランザクション上でランタイム操作の一貫性を維持するために、Microsoft 分散トランザクション コーディネーター (MSDTC) のサポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="bdec7-103">Most BizTalk Server runtime operations require Microsoft Distributed Transaction Coordinator (MSDTC) support to ensure that the operations are transactionally consistent.</span></span> <span data-ttu-id="bdec7-104">MSDTC のトランザクション サポートを使用できないと、それに関連付けられた BizTalk Server ランタイム操作を続行できません。</span><span class="sxs-lookup"><span data-stu-id="bdec7-104">If MSDTC transaction support is not available, then the associated BizTalk Server runtime operations cannot proceed.</span></span> <span data-ttu-id="bdec7-105">MSDTC トランザクション サポートが正しく構成されていない場合に一般的に影響を受ける BizTalk のコンポーネントには、シングル サインオン サービス、BizTalk ホスト インスタンス、および BizTalk Server に接続されているすべての SQL Server のインスタンスが含まれますが、これに限定されません。</span><span class="sxs-lookup"><span data-stu-id="bdec7-105">The components of BizTalk that are commonly affected when MSDTC transaction support is not configured correctly include (but are not limited to) the Single Sign-On Service, BizTalk host instances, and any SQL Server instances that are connected to by BizTalk Server.</span></span> <span data-ttu-id="bdec7-106">このセクションには、MSDTC に関連するエラーと、MSDTC の問題を診断および解決するために従う手順について説明する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bdec7-106">This section contains information that describes MSDTC related errors and steps that can be followed to diagnose and resolve problems with MSDTC.</span></span>  
  
## <a name="errors-that-can-occur-if-msdtc-transaction-support-is-not-configured-correctly"></a><span data-ttu-id="bdec7-107">MSDTC トランザクション サポートが正しく構成されていない場合に発生する可能性があるエラー</span><span class="sxs-lookup"><span data-stu-id="bdec7-107">Errors that can occur if MSDTC transaction support is not configured correctly</span></span>  
 <span data-ttu-id="bdec7-108">BizTalk 環境のコンピューターで MSDTC トランザクション サポートが正しく構成されていない場合、BizTalk Server で次のようなエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-108">Errors similar to the following may occur on BizTalk Server when MSDTC transaction support is not configured correctly on the computers in a BizTalk environment:</span></span>  
  
- <span data-ttu-id="bdec7-109">"A Microsoft Distributed Transaction Coordinator problem prevented connection to the Configuration database.</span><span class="sxs-lookup"><span data-stu-id="bdec7-109">"A Microsoft Distributed Transaction Coordinator problem prevented connection to the Configuration database.</span></span> <span data-ttu-id="bdec7-110">The transaction manager has disabled its support for remote/network transactions."</span><span class="sxs-lookup"><span data-stu-id="bdec7-110">The transaction manager has disabled its support for remote/network transactions".</span></span>  
  
- <span data-ttu-id="bdec7-111">"A Microsoft Distributed Transaction Coordinator problem prevented connection to the Configuration database.</span><span class="sxs-lookup"><span data-stu-id="bdec7-111">"A Microsoft Distributed Transaction Coordinator problem prevented connection to the Configuration database.</span></span> <span data-ttu-id="bdec7-112">The transaction has already been implicitly or explicitly committed or aborted".</span><span class="sxs-lookup"><span data-stu-id="bdec7-112">The transaction has already been implicitly or explicitly committed or aborted".</span></span>  
  
- <span data-ttu-id="bdec7-113">"Error Code: 0x8004d00a, New transaction cannot enlist in the specified transaction coordinator".</span><span class="sxs-lookup"><span data-stu-id="bdec7-113">"Error Code: 0x8004d00a, New transaction cannot enlist in the specified transaction coordinator".</span></span>  
  
- <span data-ttu-id="bdec7-114">"構成ストアからの受信場所 'MySample ReceiveLocation' に対して、トランスポートの種類のデータを取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="bdec7-114">"Could not retrieve transport type data for Receive Location 'MySample ReceiveLocation' from config store.</span></span> <span data-ttu-id="bdec7-115">プライマリ SSO サーバー 'MyServer' が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="bdec7-115">Primary SSO Server 'MyServer' failed.</span></span> <span data-ttu-id="bdec7-116">The RPC server is unavailable."</span><span class="sxs-lookup"><span data-stu-id="bdec7-116">The RPC server is unavailable".</span></span>  
  
- <span data-ttu-id="bdec7-117">"Error Code: 0x8004d025, The partner transaction manager has disabled its support for remote/network transactions".</span><span class="sxs-lookup"><span data-stu-id="bdec7-117">"Error Code: 0x8004d025, The partner transaction manager has disabled its support for remote/network transactions".</span></span>  
  
- <span data-ttu-id="bdec7-118">"Error Code: 0xc0002a24, Could not import a DTC transaction.</span><span class="sxs-lookup"><span data-stu-id="bdec7-118">"Error Code: 0xc0002a24, Could not import a DTC transaction.</span></span> <span data-ttu-id="bdec7-119">Please check that MSDTC is configured correctly for remote operation."</span><span class="sxs-lookup"><span data-stu-id="bdec7-119">Please check that MSDTC is configured correctly for remote operation".</span></span>  
  
- <span data-ttu-id="bdec7-120">"0x8004d01c</span><span class="sxs-lookup"><span data-stu-id="bdec7-120">"0x8004d01c</span></span>  
  
   <span data-ttu-id="bdec7-121">[0x1705] 内部作業項目の作成時にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bdec7-121">[0x1705] There was a failure creating the internal work item.</span></span>  
  
   <span data-ttu-id="bdec7-122">SQL Server が実行されているか確認してください。"</span><span class="sxs-lookup"><span data-stu-id="bdec7-122">Make sure that SQL Server is running."</span></span>  
  
  <span data-ttu-id="bdec7-123">MSDTC の構成エラーを解決するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bdec7-123">To resolve MSDTC configuration errors, follow the steps below.</span></span>  
  
## <a name="ensure-netbios-name-resolution-between-the-biztalk-server-and-remote-servers-is-successful"></a><span data-ttu-id="bdec7-124">BizTalk Server とリモート サーバーの間で NetBIOS 名前解決が正常に行われたことを確認する</span><span class="sxs-lookup"><span data-stu-id="bdec7-124">Ensure NetBIOS name resolution between the BizTalk Server and remote servers is successful</span></span>  
 <span data-ttu-id="bdec7-125">コンピューター間で MSDTC トランザクションを正常に実行するには、クライアント コンピューターでサーバー コンピューターの NetBIOS 名を正しい IP アドレスに解決できること、およびサーバー コンピューターでクライアント コンピューターの NetBIOS 名を正しい IP アドレスに解決できることが必要です。</span><span class="sxs-lookup"><span data-stu-id="bdec7-125">Successful MSDTC transactions between computers require that the client computer is able to resolve the NetBIOS name of the server computer to the correct IP address and the server computer is able to resolve the NetBIOS name of the client computer to the correct IP address.</span></span> <span data-ttu-id="bdec7-126">双方向 (クライアントからサーバーに対して、およびサーバーからクライアントに対して) で NetBIOS 名前解決が機能することを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-126">To verify that NetBIOS name resolution works in both directions (client to server and server to client) follow these steps:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdec7-127">NetBIOS 名と呼ばれることもよく、**ネットワーク**名。</span><span class="sxs-lookup"><span data-stu-id="bdec7-127">The NetBIOS name is also commonly referred to as the **Network** name.</span></span>  
  
1. <span data-ttu-id="bdec7-128">各コンピューターの NetBIOS 名を特定します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-128">Determine the NetBIOS name of each computer:</span></span>  
  
   1.  <span data-ttu-id="bdec7-129">右クリック**マイ コンピューター**を表示する、**システム プロパティ**ダイアログをクリックして、**コンピューター名** タブを表示する、**フル コンピューター名**、コンピューターに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-129">Right-click **My Computer** to display the **System Properties** dialog and click the **Computer Name** tab to view the **Full computer name** assigned to the computer.</span></span>  
  
   2.  <span data-ttu-id="bdec7-130">NetBIOS 名として指定した名前の最初の部分、**フル コンピューター名**たとえば場合、**フル コンピューター名**が myserver.company.domain.com、しの NetBIOS 名として表示されて、コンピューターが**myserver**します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-130">The NetBIOS name is the first portion of the name designated as the **Full computer name** so for example if the **Full computer name** is listed as myserver.company.domain.com, then the NetBIOS name of the computer is **myserver**.</span></span>  
  
2. <span data-ttu-id="bdec7-131">次のようにして、IP アドレスまたは各コンピューターに関連付けられたアドレスを特定します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-131">Determine the IP Address or addresses that are associated with each computer:</span></span>  
  
   1.  <span data-ttu-id="bdec7-132">クライアント コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-132">Launch a command prompt on the client computer, type the following command, and then press ENTER:</span></span>  
  
       ```  
       ipconfig /all  
       ```  
  
   2.  <span data-ttu-id="bdec7-133">IP アドレスまたはコンピューターに関連付けられたアドレスがコマンド プロンプト ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-133">The IP address or addresses associated with the client computer are listed in the command prompt window.</span></span>  
  
   3.  <span data-ttu-id="bdec7-134">サーバー コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-134">Launch a command prompt on the server computer, type the following command, and then press ENTER:</span></span>  
  
       ```  
       ipconfig /all  
       ```  
  
   4.  <span data-ttu-id="bdec7-135">IP アドレスまたはサーバー コンピューターに関連付けられたアドレスがコマンド プロンプト ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-135">The IP address or addresses associated with the server computer are listed in the command prompt window.</span></span>  
  
3. <span data-ttu-id="bdec7-136">各コンピューターの NetBIOS 名が、コンピューターに関連付けられている IP アドレスのいずれかに解決されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-136">Verify that the NetBIOS name of each computer is resolved to one of the IP addresses associated with the computer:</span></span>  
  
   1.  <span data-ttu-id="bdec7-137">クライアント コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-137">Launch a command prompt on the client computer, type the following command, and then press ENTER:</span></span>  
  
       ```  
       ping <NetBIOS name of server computer>  
       ```  
  
        <span data-ttu-id="bdec7-138">ping コマンドの結果として、サーバー コンピューターに関連付けられた IP アドレスが返されます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-138">The results of the ping command should return an IP address associated with the server computer.</span></span>  
  
   2.  <span data-ttu-id="bdec7-139">サーバー コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-139">Launch a command prompt on the server computer, type the following command, and then press ENTER:</span></span>  
  
       ```  
       ping <NetBIOS name of client computer>  
       ```  
  
        <span data-ttu-id="bdec7-140">ping コマンドの結果として、クライアント コンピューターに関連付けられた IP アドレスが返されます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-140">The results of the ping command should return an IP address associated with the client computer.</span></span>  
  
4. <span data-ttu-id="bdec7-141">各コンピューターの NetBIOS 名に関連付けられている IP アドレスの逆引き名前参照が正しいコンピューター名に解決されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-141">Verify that reverse name lookup of the IP address associated with the NetBIOS name on each computer resolves to the correct computer name.</span></span>  
  
   1.  <span data-ttu-id="bdec7-142">クライアント コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-142">Launch a command prompt on the client computer, type the following command, and then press ENTER:</span></span>  
  
       ```  
       ping -a <IP Address associated with client computer NetBIOS name>  
       ```  
  
        <span data-ttu-id="bdec7-143">ping コマンドの結果として、NetBIOS 名または手順 3a. で使用した NetBIOS 名に対応する完全修飾ドメイン名が返されます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-143">The results of the ping command should return a NetBIOS name or fully qualified domain name that corresponds to the NetBIOS name that was used in step 3a.</span></span> <span data-ttu-id="bdec7-144">返された名前が手順 3a. で使用した NetBIOS 名に一致しないか対応しない場合は、IP アドレスの逆引き参照は失敗し、その結果、MSDTC トランザクションがエラーになります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-144">If the name returned does not match or correspond to the NetBIOS name used in step 3a then IP address reverse lookup will fail which can cause MSDTC transactions to fail.</span></span>  
  
   2.  <span data-ttu-id="bdec7-145">サーバー コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-145">Launch a command prompt on the server computer, type the following command, and then press ENTER:</span></span>  
  
       ```  
       ping -a <IP Address associated with server computer NetBIOS name>  
       ```  
  
        <span data-ttu-id="bdec7-146">ping コマンドの結果として、NetBIOS 名または手順 3b. で使用した NetBIOS 名に対応する完全修飾ドメイン名が返されます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-146">The results of the ping command should return a NetBIOS name or fully qualified domain name that corresponds to the NetBIOS name that was used in step 3b.</span></span> <span data-ttu-id="bdec7-147">返された名前が手順 3b. で使用した NetBIOS 名に一致しないか対応しない場合は、IP アドレスの逆引き参照は失敗し、その結果、MSDTC トランザクションがエラーになります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-147">If the name returned does not match or correspond to the NetBIOS name used in step 3b then IP address reverse lookup will fail which can cause MSDTC transactions to fail.</span></span>  
  
   <span data-ttu-id="bdec7-148">NetBIOS 名前解決がいずれかの方向で失敗するか、逆引き名前参照が失敗する場合、DNS サーバー、NetBIOS ネーム サーバー、HOSTS ファイル、または LMHOSTS ファイルに適切なエントリを作成して問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-148">If NetBIOS name resolution is not successful in either direction or if reverse name lookup fails then make the appropriate entries in the DNS server, NetBIOS name server, HOSTS file, or LMHOSTS file to correct the problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdec7-149">コンピューターで使用される名前解決の方法は、コンピューターの NetBIOS ノードの型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-149">The method of name resolution used by the computer varies depending on the NetBIOS node type of the computer.</span></span> <span data-ttu-id="bdec7-150">NetBIOS ノードの種類の詳細については、[NetBIOS 名前解決](http://go.microsoft.com/fwlink/?LinkId=201638)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdec7-150">For more information about NetBIOS node types, see [NetBIOS Name Resolution](http://go.microsoft.com/fwlink/?LinkId=201638).</span></span>  
  
## <a name="ensure-that-a-firewall-between-the-biztalk-server-and-remote-servers-is-not-blocking-ports-required-for-rpc-dynamic-port-allocation"></a><span data-ttu-id="bdec7-151">BizTalk Server とリモート サーバー間のファイアウォールによって、RPC 動的ポート割り当てに必要なポートがブロックされていないことを確認する</span><span class="sxs-lookup"><span data-stu-id="bdec7-151">Ensure that a firewall between the BizTalk Server and remote servers is not blocking ports required for RPC dynamic port allocation</span></span>  
 <span data-ttu-id="bdec7-152">ネットワーク経由の MSDTC 機能は、ネットワーク経由の RPC 機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-152">MSDTC functionality over the network depends upon RPC functionality over the network.</span></span> <span data-ttu-id="bdec7-153">ファイアウォールを介した RPC 機能では、RPC の動的ポート割り当てに対応するために特定のポートが開かれていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="bdec7-153">RPC functionality through a firewall requires that specific ports are open to accommodate RPC dynamic port allocation.</span></span> <span data-ttu-id="bdec7-154">ファイアウォールが BizTalk Server とリモート サーバーの間にある場合は、次の手順では、[ファイアウォールで動作する RPC 動的ポート割り当てを構成する方法](http://go.microsoft.com/fwlink/?LinkId=66831)RPC 動的ポート割り当てに対応するためにします。</span><span class="sxs-lookup"><span data-stu-id="bdec7-154">If a firewall is in place between the BizTalk Server and remote servers, follow the steps in [How to configure RPC dynamic port allocation to work with firewalls](http://go.microsoft.com/fwlink/?LinkId=66831) to accommodate RPC dynamic port allocation.</span></span>  
  
## <a name="set-the-appropriate-msdtc-security-configuration-options"></a><span data-ttu-id="bdec7-155">適切な MSDTC セキュリティ構成オプションの設定</span><span class="sxs-lookup"><span data-stu-id="bdec7-155">Set the appropriate MSDTC Security Configuration options</span></span>  
 <span data-ttu-id="bdec7-156">Windows のセキュリティ強化により、ネットワーク経由での MSDTC へのアクセス方法を制御できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="bdec7-156">Windows provides security enhancements that govern how MSDTC is accessed over a network.</span></span> <span data-ttu-id="bdec7-157">MSDTC のセキュリティ設定を変更することにより、MSDTC とリモート コンピューター間のネットワーク経由の通信を制御できます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-157">By modifying the MSDTC security settings, you control how MSDTC communicates with remote computers over the network.</span></span> <span data-ttu-id="bdec7-158">次の表に、MSDTC のセキュリティ設定の構成時に使用できるオプションの推奨値を示します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-158">This table lists the recommended values for the options that are available when configuring MSDTC security settings:</span></span>  
  
|<span data-ttu-id="bdec7-159">構成オプション</span><span class="sxs-lookup"><span data-stu-id="bdec7-159">Configuration Option</span></span>|<span data-ttu-id="bdec7-160">既定値</span><span class="sxs-lookup"><span data-stu-id="bdec7-160">Default Value</span></span>|<span data-ttu-id="bdec7-161">推奨値</span><span class="sxs-lookup"><span data-stu-id="bdec7-161">Recommended Value</span></span>|  
|--------------------------|-------------------|-----------------------|  
|<span data-ttu-id="bdec7-162">ネットワーク DTC アクセス</span><span class="sxs-lookup"><span data-stu-id="bdec7-162">Network DTC Access</span></span>|<span data-ttu-id="bdec7-163">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-163">Disabled</span></span>|<span data-ttu-id="bdec7-164">有効</span><span class="sxs-lookup"><span data-stu-id="bdec7-164">Enabled</span></span>|  
|<span data-ttu-id="bdec7-165">**クライアントと管理**</span><span class="sxs-lookup"><span data-stu-id="bdec7-165">**Client and Administration**</span></span>|||  
|<span data-ttu-id="bdec7-166">リモート クライアントを許可する</span><span class="sxs-lookup"><span data-stu-id="bdec7-166">Allow Remote Clients</span></span>|<span data-ttu-id="bdec7-167">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-167">Disabled</span></span>|<span data-ttu-id="bdec7-168">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-168">Disabled</span></span>|  
|<span data-ttu-id="bdec7-169">リモート管理を許可する</span><span class="sxs-lookup"><span data-stu-id="bdec7-169">Allow Remote Administration</span></span>|<span data-ttu-id="bdec7-170">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-170">Disabled</span></span>|<span data-ttu-id="bdec7-171">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-171">Disabled</span></span>|  
|<span data-ttu-id="bdec7-172">**トランザクション マネージャー通信**</span><span class="sxs-lookup"><span data-stu-id="bdec7-172">**Transaction Manager Communication**</span></span>|||  
|<span data-ttu-id="bdec7-173">受信を許可する</span><span class="sxs-lookup"><span data-stu-id="bdec7-173">Allow Inbound</span></span>|<span data-ttu-id="bdec7-174">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-174">Disabled</span></span>|<span data-ttu-id="bdec7-175">有効</span><span class="sxs-lookup"><span data-stu-id="bdec7-175">Enabled</span></span>|  
|<span data-ttu-id="bdec7-176">送信を許可する</span><span class="sxs-lookup"><span data-stu-id="bdec7-176">Allow Outbound</span></span>|<span data-ttu-id="bdec7-177">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-177">Disabled</span></span>|<span data-ttu-id="bdec7-178">有効</span><span class="sxs-lookup"><span data-stu-id="bdec7-178">Enabled</span></span>|  
|<span data-ttu-id="bdec7-179">相互認証を必要とする</span><span class="sxs-lookup"><span data-stu-id="bdec7-179">Mutual Authentication Required</span></span>|<span data-ttu-id="bdec7-180">有効</span><span class="sxs-lookup"><span data-stu-id="bdec7-180">Enabled</span></span>|<span data-ttu-id="bdec7-181">すべてのリモート コンピューターで Windows Server 2003 SP1 または Windows XP SP2 以降が実行され、"相互認証を必要とする" を指定して構成されている場合は有効</span><span class="sxs-lookup"><span data-stu-id="bdec7-181">Enabled if all remote machines are running Windows Server 2003 SP1 or Windows XP SP2 or higher, and are configured with “Mutual Authentication Required”.</span></span>|  
|<span data-ttu-id="bdec7-182">着信呼び出し側には認証を必要とする</span><span class="sxs-lookup"><span data-stu-id="bdec7-182">Incoming Caller Authentication Required</span></span>|<span data-ttu-id="bdec7-183">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-183">Disabled</span></span>|<span data-ttu-id="bdec7-184">クラスター上で MSDTC を実行している場合は、有効</span><span class="sxs-lookup"><span data-stu-id="bdec7-184">Enabled if running MSDTC on cluster.</span></span>|  
|<span data-ttu-id="bdec7-185">認証を必要としない</span><span class="sxs-lookup"><span data-stu-id="bdec7-185">No Authentication Required</span></span>|<span data-ttu-id="bdec7-186">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-186">Disabled</span></span>|<span data-ttu-id="bdec7-187">リモート コンピューターで Windows Server 2003 SP1 または XP SP2 より前の OS を実行している場合は、有効</span><span class="sxs-lookup"><span data-stu-id="bdec7-187">Enabled if remote machines are pre-Windows Server 2003 SP1 or pre- Windows XP SP2.</span></span>|  
|<span data-ttu-id="bdec7-188">トランザクション インターネット プロトコル (TIP) を有効にする</span><span class="sxs-lookup"><span data-stu-id="bdec7-188">Enable TIP</span></span>|<span data-ttu-id="bdec7-189">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-189">Disabled</span></span>|<span data-ttu-id="bdec7-190">BAM ポータルを実行している場合に有効になります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-190">Enabled if running the BAM Portal.</span></span>|  
|<span data-ttu-id="bdec7-191">XA トランザクションを有効にする</span><span class="sxs-lookup"><span data-stu-id="bdec7-191">Enable XA Transactions</span></span>|<span data-ttu-id="bdec7-192">Disabled</span><span class="sxs-lookup"><span data-stu-id="bdec7-192">Disabled</span></span>|<span data-ttu-id="bdec7-193">MQSeries アダプターを使用して IBM WebSphere MQ と通信する場合など、XA ベースのトランザクション システムと通信する場合に有効になります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-193">Enabled if communicating with an XA based transactional system such as when communicating with IBM WebSphere MQ using the MQSeries adapter.</span></span>|  
  
 <span data-ttu-id="bdec7-194">これらの変更を適用した後で、MSDTC サービスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-194">After applying these changes, the MSDTC service will be restarted.</span></span>  
  
 <span data-ttu-id="bdec7-195">MSDTC セキュリティ構成オプションにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-195">To access the MSDTC security configuration options follow these steps:</span></span>  
  
1.  <span data-ttu-id="bdec7-196">をクリックして**開始**、 をクリックして**実行**、および種類**dcomcnfg**を起動する、**コンポーネント サービス**管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="bdec7-196">Click **Start**, click **Run**, and type **dcomcnfg** to launch the **Component Services**Management console.</span></span>  
  
2.  <span data-ttu-id="bdec7-197">クリックして展開**コンポーネント サービス**をクリックして展開**コンピューター**します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-197">Click to expand **Component Services** and click to expand **Computers**.</span></span>  
  
3.  <span data-ttu-id="bdec7-198">クリックして展開**マイ コンピューター**をクリックして展開**分散トランザクション コーディネーター**、右クリックして**ローカル DTC**、 をクリック**プロパティ**.</span><span class="sxs-lookup"><span data-stu-id="bdec7-198">Click to expand **My Computer**, click to expand **Distributed Transaction Coordinator**, right-click **Local DTC**, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="bdec7-199">をクリックして、**セキュリティ**のタブ、**ローカル DTC のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="bdec7-199">Click the **Security** tab of the **Local DTC Properties** dialog.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdec7-200">変更内容によっては、変更を反映するためにコンピューターの再起動が必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-200">Depending on the changes that were made, you may need to reboot the computer to enact the changes.</span></span> <span data-ttu-id="bdec7-201">変更を適用して MSDTC サービスを再起動しても問題が解消しない場合は、変更を行ったコンピューターを再起動して、確実に変更が有効になるようにします。</span><span class="sxs-lookup"><span data-stu-id="bdec7-201">If you are still encountering problems after applying changes and restarting the MSDTC service, reboot the computer on which the changes were made to ensure that the changes take effect.</span></span>  
  
 <span data-ttu-id="bdec7-202">どちらの場合、**相互認証を必要**または**着信呼び出し側の認証の必要**構成オプションが有効にし、クライアント コンピューターのアカウントを付与する必要があります、 **ネットワークからこのコンピューターにアクセス**ユーザー権限。</span><span class="sxs-lookup"><span data-stu-id="bdec7-202">If either the **Mutual Authentication Required** or the **Incoming Caller Authentication Required** configuration options are enabled then the client(s) computer account must be granted the **Access this computer from the network** user right.</span></span> <span data-ttu-id="bdec7-203">クライアント コンピューターのコンピューター アカウントが付与されていないかどうか、**ネットワークからこのコンピューターにアクセス**ユーザー権利に含まれているか、**ネットワークからこのコンピューターへのアクセスを拒否**ユーザー権利を DTCクライアントとサーバーのコンピューター間の通信は失敗します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-203">If the computer account for a client computer is not granted the **Access this computer from the network** user right, or is included in the **Deny access to this computer from the network** user right, then DTC communication between the client and server computer will fail.</span></span>  
  
 <span data-ttu-id="bdec7-204">既定の設定は、Everyone グループに与えるには、**ネットワークからこのコンピューターにアクセス**ユーザー権限。</span><span class="sxs-lookup"><span data-stu-id="bdec7-204">The default setting is to grant the Everyone group the **Access this computer from the network** user right.</span></span> <span data-ttu-id="bdec7-205">したがって、既定の設定が変更されていない限り、このユーザー権限を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bdec7-205">Therefore this user right will not need to be changed unless the default setting has been modified.</span></span> <span data-ttu-id="bdec7-206">場合、**認証を必要としない**構成オプションが有効になっている、**ネットワークからこのコンピューターにアクセス**ユーザー権利は、クライアント コンピューターのアカウントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="bdec7-206">If the **No Authentication Required** configuration option is enabled then the **Access this computer from the network** user right does not apply to the client(s) computer account.</span></span>  
  
 <span data-ttu-id="bdec7-207">"ネットワーク経由でコンピューターへアクセス" ユーザー権限を付与されるユーザーまたはグループを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-207">To change the users or groups that are granted the "Access this computer from the network" user right, follow these steps:</span></span>  
  
1. <span data-ttu-id="bdec7-208">をクリックして**開始**、 をクリックして**実行**、型**Gpedit.msc**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="bdec7-208">Click **Start**, click **Run**, type **Gpedit.msc**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="bdec7-209">ローカル コンピューターのポリシー一覧で次の項目を展開します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-209">Expand the following items in the Local Computer Policy list:</span></span>  
  
   -   <span data-ttu-id="bdec7-210">コンピューターの構成</span><span class="sxs-lookup"><span data-stu-id="bdec7-210">Computer Configuration</span></span>  
  
   -   <span data-ttu-id="bdec7-211">Windows の設定</span><span class="sxs-lookup"><span data-stu-id="bdec7-211">Windows Settings</span></span>  
  
   -   <span data-ttu-id="bdec7-212">セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="bdec7-212">Security Settings</span></span>  
  
   -   <span data-ttu-id="bdec7-213">ローカル ポリシー</span><span class="sxs-lookup"><span data-stu-id="bdec7-213">Local Policies</span></span>  
  
3. <span data-ttu-id="bdec7-214">クリックして**ユーザー権利の割り当て**します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-214">Click **User Rights Assignment**.</span></span>  
  
4. <span data-ttu-id="bdec7-215">ダブルクリック**ネットワークからこのコンピューターにアクセス**、順にクリックします**追加のユーザーまたはグループ**します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-215">Double-click **Access this computer from the network**, and then click **Add User or Group**.</span></span>  
  
5. <span data-ttu-id="bdec7-216">をクリックして**オブジェクトの種類**を選択します**コンピューター**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-216">Click **Object Types**, select **Computers** and click **OK**.</span></span>  
  
6. <span data-ttu-id="bdec7-217">コンピューター名またはグループ名の追加、**を選択するオブジェクト名の入力**領域。</span><span class="sxs-lookup"><span data-stu-id="bdec7-217">Add the computer name or the group name in the **Enter the object names to select** area.</span></span>  
  
7. <span data-ttu-id="bdec7-218">クリックして**名前の確認**をエントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-218">Click **Check Names** to verify the entry.</span></span>  
  
8. <span data-ttu-id="bdec7-219">**[OK]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="bdec7-219">Click **OK** twice.</span></span>  
  
   <span data-ttu-id="bdec7-220">ユーザーまたはグループに含まれている変更を**ネットワークからこのコンピューターへのアクセスを拒否**ユーザー権利をこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bdec7-220">To change the users or groups that are included in the **Deny access to this computer from the network** user right, follow these steps:</span></span>  
  
9. <span data-ttu-id="bdec7-221">ローカル コンピューターのポリシー一覧で次の項目を展開します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-221">Expand the following items in the Local Computer Policy list:</span></span>  
  
   -   <span data-ttu-id="bdec7-222">コンピューターの構成</span><span class="sxs-lookup"><span data-stu-id="bdec7-222">Computer Configuration</span></span>  
  
   -   <span data-ttu-id="bdec7-223">Windows の設定</span><span class="sxs-lookup"><span data-stu-id="bdec7-223">Windows Settings</span></span>  
  
   -   <span data-ttu-id="bdec7-224">セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="bdec7-224">Security Settings</span></span>  
  
   -   <span data-ttu-id="bdec7-225">ローカル ポリシー</span><span class="sxs-lookup"><span data-stu-id="bdec7-225">Local Policies</span></span>  
  
10. <span data-ttu-id="bdec7-226">クリックして**ユーザー権利の割り当て**します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-226">Click **User Rights Assignment**.</span></span>  
  
11. <span data-ttu-id="bdec7-227">ダブルクリック**このコンピューターをネットワークからのアクセスを拒否**コンピューター名またはこのユーザー権限から削除するグループを選択する順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdec7-227">Double-click **Deny access this computer from the network**, and then click to select the computer name or group that you want to remove from this user right.</span></span>  
  
12. <span data-ttu-id="bdec7-228">クリックして**削除**順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-228">Click **Remove** and then click **OK**.</span></span>  
  
## <a name="set-the-appropriate-values-for-the-enableauthepresolution-and-restrictremoteclients-options"></a><span data-ttu-id="bdec7-229">EnableAuthEpResolution オプションと RestrictRemoteClients オプションに、適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-229">Set the appropriate values for the EnableAuthEpResolution and RestrictRemoteClients options</span></span>  
 <span data-ttu-id="bdec7-230">Windows のセキュリティ強化により、RPC インターフェイスへは必ず認証された呼び出しを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-230">Windows enhances security by requiring authenticated calls to the RPC interface.</span></span> <span data-ttu-id="bdec7-231">この機能を使用して構成できますが、 **EnableAuthEpResolution**と**RestrictRemoteClients**レジストリ キー。</span><span class="sxs-lookup"><span data-stu-id="bdec7-231">This functionality is configurable through the **EnableAuthEpResolution** and **RestrictRemoteClients** registry keys.</span></span> <span data-ttu-id="bdec7-232">リモート コンピューターが RPC インターフェイスにアクセスできるように、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-232">To ensure that remote computers are able to access the RPC interface, follow these steps:</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bdec7-233">レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-233">Incorrect use of Registry Editor may cause problems requiring you to reinstall your operating system.</span></span> <span data-ttu-id="bdec7-234">レジストリ エディターは、ご自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="bdec7-234">Use Registry Editor at your own risk.</span></span> <span data-ttu-id="bdec7-235">バックアップ、復元、およびレジストリを変更する方法の詳細についてで、マイクロソフト サポート技術情報記事「Microsoft Windows レジストリの説明」を参照して[Microsoft Windows レジストリの説明](http://go.microsoft.com/fwlink/?LinkId=62729)します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-235">For more information about how to back up, restore, and modify the registry, see the Microsoft Knowledge Base article "Description of the Microsoft Windows registry" at [Description of the Microsoft Windows registry](http://go.microsoft.com/fwlink/?LinkId=62729).</span></span>  
  
1.  <span data-ttu-id="bdec7-236">をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリックします**ok**レジストリ エディターを起動します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-236">Click **Start**, click **Run**, type **regedit.exe**, and then click **OK** to start Registry Editor.</span></span>  
  
     <span data-ttu-id="bdec7-237">移動します**\software\policies\microsoft\windows NT**</span><span class="sxs-lookup"><span data-stu-id="bdec7-237">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows NT**</span></span>  
  
2.  <span data-ttu-id="bdec7-238">で、 **RPC**キーの値を持つ、次の DWORD エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-238">Under the **RPC** key, create the following DWORD entries with the indicated values.</span></span> <span data-ttu-id="bdec7-239">場合、 **RPC**キーが存在しないし、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-239">If the **RPC** key does not exist then it must be created.</span></span>  
  
    |<span data-ttu-id="bdec7-240">DWORD エントリ</span><span class="sxs-lookup"><span data-stu-id="bdec7-240">DWORD entry</span></span>|<span data-ttu-id="bdec7-241">既定値</span><span class="sxs-lookup"><span data-stu-id="bdec7-241">Default value</span></span>|<span data-ttu-id="bdec7-242">推奨値</span><span class="sxs-lookup"><span data-stu-id="bdec7-242">Recommended value</span></span>|  
    |-----------------|-------------------|-----------------------|  
    |<span data-ttu-id="bdec7-243">EnableAuthEpResolution</span><span class="sxs-lookup"><span data-stu-id="bdec7-243">EnableAuthEpResolution</span></span>|<span data-ttu-id="bdec7-244">0 (無効)</span><span class="sxs-lookup"><span data-stu-id="bdec7-244">0 (disabled)</span></span>|<span data-ttu-id="bdec7-245">1</span><span class="sxs-lookup"><span data-stu-id="bdec7-245">1</span></span>|  
    |<span data-ttu-id="bdec7-246">RestrictRemoteClients</span><span class="sxs-lookup"><span data-stu-id="bdec7-246">RestrictRemoteClients</span></span>|<span data-ttu-id="bdec7-247">1 (有効)</span><span class="sxs-lookup"><span data-stu-id="bdec7-247">1 (enabled)</span></span>|<span data-ttu-id="bdec7-248">0</span><span class="sxs-lookup"><span data-stu-id="bdec7-248">0</span></span>|  
  
3.  <span data-ttu-id="bdec7-249">レジストリ エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-249">Close Registry Editor.</span></span>  
  
4.  <span data-ttu-id="bdec7-250">MSDTC サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-250">Restart the MSDTC Service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdec7-251">変更内容によっては、変更を反映するためにコンピューターの再起動が必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-251">Depending on the changes that were made, you may need to reboot the computer to enact the changes.</span></span> <span data-ttu-id="bdec7-252">変更を適用して MSDTC サービスを再起動しても問題が解消しない場合は、変更を行ったコンピューターを再起動して、確実に変更が有効になるようにします。</span><span class="sxs-lookup"><span data-stu-id="bdec7-252">If you are still encountering problems after applying changes and restarting the MSDTC service, reboot the computer on which the changes were made to ensure that the changes take effect.</span></span>  
  
## <a name="if-windows-firewall-is-running-add-an-exception-for-the-msdtc-service"></a><span data-ttu-id="bdec7-253">Windows ファイアウォールが実行中の場合は、MSDTC サービスの例外を追加します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-253">If Windows Firewall is running, add an exception for the MSDTC service</span></span>  
 <span data-ttu-id="bdec7-254">Windows ファイアウォール サービスが、コンピューター間の MSDTC 通信をブロックする場合があります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-254">The Windows Firewall service may block MSDTC communications between computers.</span></span> <span data-ttu-id="bdec7-255">Windows ファイアウォールが稼働している場合にコンピューター間で MSDTC 通信がブロックされないようにするには、Windows ファイアウォールの例外リストに msdtc.exe を追加します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-255">To ensure that MSDTC communications are not blocked between computers, add msdtc.exe to the Windows Firewall exception list if the Windows Firewall service is running.</span></span>  
  
1.  <span data-ttu-id="bdec7-256">をクリックして**開始**、 をクリックして**実行**、型**firewall.cpl**、順にクリックします**OK**を表示する、 **Windows ファイアウォール**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bdec7-256">Click **Start**, click **Run**, type **firewall.cpl**, and then click **OK** to display the **Windows Firewall** dialog box.</span></span>  
  
2.  <span data-ttu-id="bdec7-257">クリックして**Windows ファイアウォールによるプログラムの許可**を表示する、 **Windows ファイアウォールの設定** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bdec7-257">Click **Allow a program through the Windows Firewall** to display the **Windows Firewall Settings** dialog box.</span></span>  
  
3.  <span data-ttu-id="bdec7-258">をクリックして、**例外**のタブ、 **Windows ファイアウォールの設定** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bdec7-258">Click the **Exceptions** tab of the **Windows Firewall Settings** dialog box.</span></span>  
  
4.  <span data-ttu-id="bdec7-259">クリックして**プログラムの追加**を表示する、**プログラムの追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bdec7-259">Click **Add Program** to display the **Add a Program** dialog box.</span></span>  
  
5.  <span data-ttu-id="bdec7-260">クリックして**参照**に移動します *%system32*\msdtc.exe します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-260">Click **Browse** and navigate to *%system32%* \msdtc.exe.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bdec7-261">コマンド プロンプト ウィンドウで「を起動**echo system32%** キーを押します**Enter**このコンピューター上の \System32 ディレクトリの場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-261">Launch a command prompt, type **echo %system32%** and press **Enter** to determine the location of the \System32 directory on this computer.</span></span>  
  
6.  <span data-ttu-id="bdec7-262">クリックして選択**msdtc.exe**クリック**オープン**。</span><span class="sxs-lookup"><span data-stu-id="bdec7-262">Click to select **msdtc.exe** and click **Open**.</span></span>  
  
7.  <span data-ttu-id="bdec7-263">をクリックして**スコープを変更する**msdtc 通信を許可し、をクリックして、コンピューターのセットを指定する**OK**します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-263">Click **Change scope** to specify the set of computers for which MSDTC communications should be allowed and click **OK**.</span></span>  
  
8.  <span data-ttu-id="bdec7-264">をクリックして**OK**で、**プログラムの追加** ダイアログ ボックスをクリックします**ok**で、 **Windows ファイアウォールの設定** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bdec7-264">Click **OK** in the **Add a Program** dialog box and click **OK** in the **Windows Firewall Settings** dialog box.</span></span>  
  
9. <span data-ttu-id="bdec7-265">閉じる、 **Windows ファイアウォール** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bdec7-265">Close the **Windows Firewall** dialog box.</span></span>  
  
10. <span data-ttu-id="bdec7-266">分散トランザクション コーディネーター サービスを停止して再起動します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-266">Stop and restart the Distributed Transaction Coordinator service.</span></span>  
  
    -   <span data-ttu-id="bdec7-267">コマンド プロンプト ウィンドウで「を起動**net stop msdtc**キーを押します**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-267">Launch a command prompt, type **net stop msdtc** and press **Enter**.</span></span>  
  
    -   <span data-ttu-id="bdec7-268">分散トランザクション コーディネーター サービスが停止後に「 **msdtc を開始する net**キーを押します **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-268">After the Distributed Transaction Coordinator service has stopped, type **net start msdtc** and press **Enter**.</span></span>  
  
## <a name="use-dtctester-or-dtcping-to-verify-msdtc-functionality-over-the-network"></a><span data-ttu-id="bdec7-269">DTCTester または DTCPing を使用して、ネットワーク上で MSDTC 機能を確認する</span><span class="sxs-lookup"><span data-stu-id="bdec7-269">Use DTCTester or DTCPing to verify MSDTC functionality over the network</span></span>  
 <span data-ttu-id="bdec7-270">2 台のコンピューターのうちの 1 台に SQL Server がインストールされている場合は、DTCTester ユーティリティを使用してそれらのコンピューター間のトランザクション サポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-270">Use the DTCTester utility to verify transaction support between two computers if SQL Server is installed on one of the computers.</span></span> <span data-ttu-id="bdec7-271">DTCTester ユーティリティでは、ODBC を使用して SQL Server データベースのトランザクション サポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-271">The DTCTester utility uses ODBC to verify transaction support against a SQL Server database.</span></span> <span data-ttu-id="bdec7-272">DTCTester の詳細については、[DTCTester ツールの使用方法](http://go.microsoft.com/fwlink/?LinkId=66232)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdec7-272">For more information about DTCTester see [How to Use DTCTester Tool](http://go.microsoft.com/fwlink/?LinkId=66232).</span></span>  
  
 <span data-ttu-id="bdec7-273">2 台のコンピューターのどちらにも SQL Server がインストールされていない場合は、DTCPing を使用してそれらのコンピューター間のトランザクション サポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-273">Use DTCPing to verify transaction support between two computers if SQL Server is not installed on either computer.</span></span> <span data-ttu-id="bdec7-274">DTCPing ツールは、クライアント コンピューターとサーバー コンピューターの両方で実行する必要があります。いずれのコンピューターにも SQL Server がインストールされていない場合は、DTCTester ユーティリティの適切な代替手段になります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-274">The DTCPing tool must be run on both the client and server computer and is a good alternative to the DTCTester utility when SQL Server is not installed on either computer.</span></span> <span data-ttu-id="bdec7-275">DTCPing の詳細については、[MS DTC ファイアウォールの問題のトラブルシューティングを行う方法](http://go.microsoft.com/fwlink/?LinkId=61915)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdec7-275">For more information about DTCPing, see [How to troubleshoot MS DTC firewall issues](http://go.microsoft.com/fwlink/?LinkId=61915).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bdec7-276">DTCPing には、警告が返された場合を"警告: テストの両方のコンピューターの CID 値が同じ"し、セクションの手順に従います**MSDTC に一意の CID 値が割り当てられていることを確認**対応の間で MSDTC が正しく機能するためにテスト マシン。</span><span class="sxs-lookup"><span data-stu-id="bdec7-276">If DTCPing returns the warning that “WARNING:the CID values for both test machines are the same” then follow the steps in the section **Ensure that MSDTC is assigned a unique CID value** to accommodate proper MSDTC functionality between the test machines.</span></span>  
  
## <a name="ensure-that-msdtc-is-assigned-a-unique-cid-value"></a><span data-ttu-id="bdec7-277">MSDTC に一意の CID 値が割り当てられていることを確認する</span><span class="sxs-lookup"><span data-stu-id="bdec7-277">Ensure that MSDTC is assigned a unique CID value</span></span>  
 <span data-ttu-id="bdec7-278">Windows オペレーティング システムの MSDTC 機能がコンピューター間で正しく動作するには、一意の CID 値が必要です。</span><span class="sxs-lookup"><span data-stu-id="bdec7-278">The MSDTC feature of the Windows operating system requires unique CID values to ensure that MSDTC functionality between computers works correctly.</span></span> <span data-ttu-id="bdec7-279">Windows インストールのディスクの重複イメージには一意の CID 値が必要です。この値がないと、MSDTC 機能が損なわれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-279">Disk duplicate images of Windows installations must have unique CID values or MSDTC functionality may be impaired.</span></span> <span data-ttu-id="bdec7-280">この状況は、仮想ハード ディスクを使用して仮想マシンにオペレーティング システムを配置した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-280">This can occur when using virtual hard disks to deploy an operating system to a virtual machine.</span></span>  
  
 <span data-ttu-id="bdec7-281">Windows オペレーティング システムを実行しているコンピューターの MSDTC CID 値が一意かどうかを判定するには、両方のコンピューター上で、HKEY_CLASSES_ROOT\CID レジストリ キーの下のエントリの値を調べます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-281">To determine if MSDTC CID values for computers that are running the Windows operating system are unique, check the values for the entries under the HKEY_CLASSES_ROOT\CID registry key on both computers.</span></span> <span data-ttu-id="bdec7-282">これらの値が各コンピューターに対して一意でない場合、セクションの手順に従ってください**他のトラブルシューティングの手順に失敗した場合は、分散トランザクション コーディネーター サービスを再インストールを検討してください**を 1 つで MSDTC を再インストールするには。でコンピューターがそのコンピューターの一意の MSDTC CID 値を生成し、適切な MSDTC 操作に対応します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-282">If these values are not unique for each computer then follow the steps in the section **Consider reinstalling the Distributed Transaction Coordinator service if other troubleshooting steps are not successful** to reinstall MSDTC on one of the computers, which will then generate unique MSDTC CID values for that computer and accommodate proper MSDTC operations.</span></span>  
  
## <a name="error-new-transaction-cannot-enlist-in-the-specified-transaction-coordinator-0x8004d00a-occurs-if-the-msdtc-connection-between-a-client-computer-and-a-server-computer-is-closed"></a><span data-ttu-id="bdec7-283">"New transaction cannot enlist in the specified transaction coordinator (0x8004d00a)" というエラーの発生 (クライアント コンピューターとサーバー コンピューターの間の MSDTC 接続が閉じられた場合)</span><span class="sxs-lookup"><span data-stu-id="bdec7-283">Error “New transaction cannot enlist in the specified transaction coordinator (0x8004d00a)” occurs if the MSDTC connection between a client computer and a server computer is closed</span></span>  
 <span data-ttu-id="bdec7-284">特定のシナリオでは、クライアントとサーバー間の既存の MSDTC 接続が閉じられると、後続のこの接続を使用すると、次のエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="bdec7-284">In certain scenarios, it is possible that an existing MSDTC connection between a client and server is closed and subsequent attempts to use this connection will result in the following error message:</span></span>  
<span data-ttu-id="bdec7-285">新しいトランザクションが、指定されたトランザクション コーディネーター (0x8004d00a) に参加できませんでした。</span><span class="sxs-lookup"><span data-stu-id="bdec7-285">New transaction cannot enlist in the specified transaction coordinator (0x8004d00a)</span></span>  
<span data-ttu-id="bdec7-286">詳細については、[MS DTC でトランザクションを開始しようとすると、エラー メッセージ:"新しい transaction cannot enlist in the specified transaction coordinator"](http://support.microsoft.com/kb/922430)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdec7-286">For more information, see [Error message when you try to start a transaction in MS DTC: "New transaction cannot enlist in the specified transaction coordinator"](http://support.microsoft.com/kb/922430).</span></span>  
  
## <a name="consider-reinstalling-the-distributed-transaction-coordinator-service-if-other-troubleshooting-steps-are-not-successful"></a><span data-ttu-id="bdec7-287">その他のトラブルシューティングの手順が正常に実行されない場合は、分散トランザクション コーディネーター サービスの再インストールを検討してください。</span><span class="sxs-lookup"><span data-stu-id="bdec7-287">Consider reinstalling the Distributed Transaction Coordinator service if other troubleshooting steps are not successful</span></span>  
 <span data-ttu-id="bdec7-288">MSDTC を使用したトラブルシューティングで問題が解決されなかった場合は、MSDTC のアンインストールおよび再インストールを検討してください。</span><span class="sxs-lookup"><span data-stu-id="bdec7-288">If other attempts at troubleshooting problems with MSDTC are not successful consider uninstalling and reinstalling MSDTC.</span></span> <span data-ttu-id="bdec7-289">MSDTC のアンインストールおよび再インストールを行うには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bdec7-289">Follow these steps to uninstall and reinstall MSDTC:</span></span>  
  
1.  <span data-ttu-id="bdec7-290">管理者としてコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="bdec7-290">Open a command prompt as Administrator.</span></span>  
  
2.  <span data-ttu-id="bdec7-291">コマンド プロンプトで、分散トランザクション コーディネーター サービスをアンインストールするには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-291">At the command prompt, type the following to uninstall the Distributed Transaction Coordinator service:</span></span>  
    `msdtc -uninstall`  
  
3.  <span data-ttu-id="bdec7-292">コマンド プロンプトで、分散トランザクション コーディネーター サービスをインストールするのには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="bdec7-292">At the command prompt, type the following to install the Distributed Transaction Coordinator service:</span></span>  
    `msdtc –install`  
  
> [!IMPORTANT]
>  <span data-ttu-id="bdec7-293">MSDTC を再インストールすると、分散トランザクション コーディネーター サービスの既定の動作が変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-293">Reinstalling MSDTC may change the default behavior of the Distributed Transaction Coordinator service.</span></span> <span data-ttu-id="bdec7-294">MSDTC の再インストール後に、以下の手順に従って、分散トランザクション コーディネーター サービスが正しく動作することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bdec7-294">Follow these steps after reinstalling MSDTC to ensure that the Distributed Transaction Coordinator service works correctly:</span></span>  
> 
> - <span data-ttu-id="bdec7-295">MSDTC を再インストールすると、MSDTC セキュリティ構成オプションが既定値にリセットされることがあります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-295">Reinstalling MSDTC may reset MSDTC Security Configuration options back to default values.</span></span> <span data-ttu-id="bdec7-296">MSDTC の再インストール後に、MSDTC セキュリティ構成オプションが適切な値に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bdec7-296">Verify that the MSDTC Security Configuration options are set to the appropriate values after reinstalling MSDTC.</span></span>  
>   -   <span data-ttu-id="bdec7-297">MSDTC の再インストールを変更することがあります、**スタートアップの種類**分散トランザクション コーディネーター サービスの値。</span><span class="sxs-lookup"><span data-stu-id="bdec7-297">Reinstalling MSDTC may change the **Startup Type** value for the Distributed Transaction Coordinator service.</span></span> <span data-ttu-id="bdec7-298">いることを確認、**スタートアップの種類**値に設定されている分散トランザクション コーディネーター サービスの**自動**MSDTC を再インストール後にします。</span><span class="sxs-lookup"><span data-stu-id="bdec7-298">Verify that the **Startup Type** value for the Distributed Transaction Coordinator service is set to **Automatic** after reinstalling MSDTC.</span></span>  
>   -   <span data-ttu-id="bdec7-299">MSDTC を再インストールするには、コンピューターを再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bdec7-299">Reinstalling MSDTC may require a reboot of the computer.</span></span> <span data-ttu-id="bdec7-300">分散トランザクション コーディネーター サービスを正しく動作させるには、MSDTC の再インストール後にコンピューターを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="bdec7-300">To ensure that the Distributed Transaction Coordinator service works correctly, reboot the computer after reinstalling MSDTC.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdec7-301">参照</span><span class="sxs-lookup"><span data-stu-id="bdec7-301">See Also</span></span>  
 <span data-ttu-id="bdec7-302">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="bdec7-302">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="bdec7-303">Windows Server クラスターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bdec7-303">Troubleshooting a Windows Server Cluster</span></span>](../core/troubleshooting-a-windows-server-cluster.md)