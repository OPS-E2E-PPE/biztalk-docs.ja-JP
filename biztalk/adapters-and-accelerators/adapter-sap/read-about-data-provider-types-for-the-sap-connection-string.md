---
title: "SAP 接続文字列のデータ プロバイダーの種類の説明を読む |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, connection string
- ADO, connection string
ms.assetid: 7a46eaae-604f-4bae-924b-9f6d43a6e8a0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1a27fa8b09addc7874e6056f0b467c7f874a41e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="read-about-data-provider-types-for-the-sap-connection-string"></a><span data-ttu-id="e8c37-102">SAP 接続文字列のデータ プロバイダーの種類の説明を読む</span><span class="sxs-lookup"><span data-stu-id="e8c37-102">Read about Data Provider types for the SAP Connection String</span></span>
<span data-ttu-id="e8c37-103">SAP システムへの接続を確立するには、ときは、接続文字列の形式で ADO.NET クライアントが SAP 接続のプロパティを指定してください。</span><span class="sxs-lookup"><span data-stu-id="e8c37-103">To establish connectivity to an SAP system, ADO.NET clients must specify the SAP connection properties in the form of a connection string.</span></span> <span data-ttu-id="e8c37-104">SAP ADO 接続文字列の形式は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="e8c37-104">The format for the SAP ADO connection string looks like:</span></span>  
  
```  
[Property1]=[Value1];[Property2]=[Value2];....  
```  
  
 <span data-ttu-id="e8c37-105">使用して SAP システムへの接続への接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次の種類を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="e8c37-105">The connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] can have the following types:</span></span>  
  
-   <span data-ttu-id="e8c37-106">**タイプ a:**アプリケーション ホスト ベース接続を使用するアプリケーション サーバーを指定する接続 URI、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="e8c37-106">**TYPE A:** An application host–based connection in which the connection URI specifies an application server through which the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] connects to the SAP system.</span></span>  
  
-   <span data-ttu-id="e8c37-107">**タイプ b:**負荷分散の接続を経由するメッセージ サーバーを指定する接続 URI、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="e8c37-107">**TYPE B:** A load-balanced connection in which the connection URI specifies a message server through which the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] connects to the SAP system.</span></span>  
  
-   <span data-ttu-id="e8c37-108">**種類 d:**先ベースの接続を接続 URI が SAP システムの接続パラメーターを含む saprfc.ini ファイルの保存先を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8c37-108">**TYPE D:** A destination-based connection in which the connection URI specifies a destination in the saprfc.ini file that contains the connection parameters for the SAP system.</span></span>  
  
 <span data-ttu-id="e8c37-109">次の表では、接続 URI にこれらの接続を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8c37-109">The following table describes how these connections are specified in the connection URI.</span></span>  
  
|<span data-ttu-id="e8c37-110">TYPE</span><span class="sxs-lookup"><span data-stu-id="e8c37-110">TYPE</span></span>|<span data-ttu-id="e8c37-111">プロパティ 1</span><span class="sxs-lookup"><span data-stu-id="e8c37-111">Property 1</span></span>|<span data-ttu-id="e8c37-112">プロパティ 2</span><span class="sxs-lookup"><span data-stu-id="e8c37-112">Property 2</span></span>|<span data-ttu-id="e8c37-113">Description</span><span class="sxs-lookup"><span data-stu-id="e8c37-113">Description</span></span>|  
|----------|----------------|----------------|-----------------|  
|<span data-ttu-id="e8c37-114">A</span><span class="sxs-lookup"><span data-stu-id="e8c37-114">A</span></span>|<span data-ttu-id="e8c37-115">ASHOST (アプリケーション サーバーのホスト)</span><span class="sxs-lookup"><span data-stu-id="e8c37-115">ASHOST (Application Server Host)</span></span>|<span data-ttu-id="e8c37-116">SYSNR (SAP システム番号)</span><span class="sxs-lookup"><span data-stu-id="e8c37-116">SYSNR (SAP System Number)</span></span>|<span data-ttu-id="e8c37-117">アプリケーション ホスト ベース接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8c37-117">Specifies an application host-based connection.</span></span>|  
|<span data-ttu-id="e8c37-118">B</span><span class="sxs-lookup"><span data-stu-id="e8c37-118">B</span></span>|<span data-ttu-id="e8c37-119">MSHOST (メッセージ サーバー ホスト)</span><span class="sxs-lookup"><span data-stu-id="e8c37-119">MSHOST (Message Server Host)</span></span>|<span data-ttu-id="e8c37-120">R3NAME (SAP R3 名)</span><span class="sxs-lookup"><span data-stu-id="e8c37-120">R3NAME (SAP R3 Name)</span></span>|<span data-ttu-id="e8c37-121">負荷分散のメッセージ サーバー経由の接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8c37-121">Specifies a load balancing connection through a message server.</span></span> <span data-ttu-id="e8c37-122">負荷分散の接続では、省略可能なサーバー グループを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e8c37-122">For a load balancing connection, an optional server group can be specified.</span></span>|  
|<span data-ttu-id="e8c37-123">D</span><span class="sxs-lookup"><span data-stu-id="e8c37-123">D</span></span>|<span data-ttu-id="e8c37-124">追加先 (宛先 saprfc.ini ファイルの接続パラメーターが含まれています)</span><span class="sxs-lookup"><span data-stu-id="e8c37-124">DEST (Destination that contains the connection parameters in the saprfc.ini file)</span></span>|-|<span data-ttu-id="e8c37-125">移行先ベースの接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8c37-125">Specifies a destination-based connection.</span></span> <span data-ttu-id="e8c37-126">Saprfc.ini ファイルで指定したコピー先には、SAP 接続パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8c37-126">The SAP connection parameters are contained in the specified destination in the saprfc.ini file.</span></span> <span data-ttu-id="e8c37-127">マップ先の型 A と B の種類の接続のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8c37-127">Only TYPE A and TYPE B connections can be specified in the destination.</span></span> <span data-ttu-id="e8c37-128">**注:** saprfc.ini ファイルの接続の値を指定する場合は、ファイルにアクセスする .exe または SAP システムで必要とする標準の場所では、同じフォルダーに保存されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e8c37-128">**Note:**  If you specify connection values in the saprfc.ini file, make sure the file is located in the same folder as the .exe that accesses the file or at a standard location as required by the SAP system.</span></span> <span data-ttu-id="e8c37-129">詳細については、SAP のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8c37-129">For more information, see the SAP documentation.</span></span>|  
  
 <span data-ttu-id="e8c37-130">接続を使用して SAP システムへの接続への接続文字列の種類に基づいて、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のプロパティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e8c37-130">Based on the type of connection, the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] can contain the following properties.</span></span>  
  
|<span data-ttu-id="e8c37-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e8c37-131">Property</span></span>|<span data-ttu-id="e8c37-132">型の使用</span><span class="sxs-lookup"><span data-stu-id="e8c37-132">Used for TYPE</span></span>|<span data-ttu-id="e8c37-133">Description</span><span class="sxs-lookup"><span data-stu-id="e8c37-133">Description</span></span>|  
|--------------|-------------------|-----------------|  
|<span data-ttu-id="e8c37-134">アプリケーション サーバーのホスト (ASHOST)</span><span class="sxs-lookup"><span data-stu-id="e8c37-134">Application Server Host (ASHOST)</span></span>|<span data-ttu-id="e8c37-135">A</span><span class="sxs-lookup"><span data-stu-id="e8c37-135">A</span></span>|<span data-ttu-id="e8c37-136">SAP アプリケーション サーバー ホストの名前です。</span><span class="sxs-lookup"><span data-stu-id="e8c37-136">Name of the SAP application server host.</span></span>|  
|<span data-ttu-id="e8c37-137">システム番号 (SYSNR)</span><span class="sxs-lookup"><span data-stu-id="e8c37-137">System Number (SYSNR)</span></span>|<span data-ttu-id="e8c37-138">A</span><span class="sxs-lookup"><span data-stu-id="e8c37-138">A</span></span>|<span data-ttu-id="e8c37-139">SAP システム番号</span><span class="sxs-lookup"><span data-stu-id="e8c37-139">The SAP system number</span></span>|  
|<span data-ttu-id="e8c37-140">アプリケーション サーバー グループ名 (グループ)</span><span class="sxs-lookup"><span data-stu-id="e8c37-140">Application Server Group Name (GROUP)</span></span>|<span data-ttu-id="e8c37-141">B</span><span class="sxs-lookup"><span data-stu-id="e8c37-141">B</span></span>|<span data-ttu-id="e8c37-142">SAP サーバー グループの名前。</span><span class="sxs-lookup"><span data-stu-id="e8c37-142">Name of the SAP server group.</span></span> <span data-ttu-id="e8c37-143">これは、負荷分散の接続内のアプリケーション サーバーの任意のグループです。</span><span class="sxs-lookup"><span data-stu-id="e8c37-143">This is an optional group of application servers in a load balancing connection.</span></span>|  
|<span data-ttu-id="e8c37-144">メッセージ サーバー ホスト (MSHOST)</span><span class="sxs-lookup"><span data-stu-id="e8c37-144">Message Server Host (MSHOST)</span></span>|<span data-ttu-id="e8c37-145">B</span><span class="sxs-lookup"><span data-stu-id="e8c37-145">B</span></span>|<span data-ttu-id="e8c37-146">SAP メッセージ サーバー ホストの名前</span><span class="sxs-lookup"><span data-stu-id="e8c37-146">Name of the SAP message server host</span></span>|  
|<span data-ttu-id="e8c37-147">メッセージ サーバー サービス (MSSERV)</span><span class="sxs-lookup"><span data-stu-id="e8c37-147">Message Server Service (MSSERV)</span></span>|<span data-ttu-id="e8c37-148">B</span><span class="sxs-lookup"><span data-stu-id="e8c37-148">B</span></span>|<span data-ttu-id="e8c37-149">指定されている SAP メッセージ サーバー サービスの名前、\<システム ドライブ >: \WINDOWS\system32\drivers\etc\services ファイル。</span><span class="sxs-lookup"><span data-stu-id="e8c37-149">Name of the SAP message server service as specified in the \<system drive>:\WINDOWS\system32\drivers\etc\services file.</span></span> <span data-ttu-id="e8c37-150">値を指定しない場合、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]これがあることを前提としています"いる sapms\<R/3 システム名 >"です。</span><span class="sxs-lookup"><span data-stu-id="e8c37-150">If you do not specify a value, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] assumes this to be "sapms\<R/3 system name>".</span></span> <span data-ttu-id="e8c37-151">たとえば、R/3 システム名が DV1 の場合は、アダプターはメッセージ サーバーのサービス名"sapmsDV1"であると仮定します。</span><span class="sxs-lookup"><span data-stu-id="e8c37-151">For example, if the R/3 system name is DV1, the adapter assumes the message server service name to be "sapmsDV1".</span></span><br /><br /> <span data-ttu-id="e8c37-152">ただし、サービス ファイルのエントリが異なる場合は、その値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8c37-152">However, if the entry in the services file is different, you must specify that value.</span></span>|  
|<span data-ttu-id="e8c37-153">R/3 システム名 (R3NAME)</span><span class="sxs-lookup"><span data-stu-id="e8c37-153">R/3 System Name (R3NAME)</span></span>|<span data-ttu-id="e8c37-154">B</span><span class="sxs-lookup"><span data-stu-id="e8c37-154">B</span></span>|<span data-ttu-id="e8c37-155">SAP R/3 の名前です。</span><span class="sxs-lookup"><span data-stu-id="e8c37-155">The SAP R/3 name.</span></span>|  
|<span data-ttu-id="e8c37-156">移行先 (追加先)</span><span class="sxs-lookup"><span data-stu-id="e8c37-156">Destination (DEST)</span></span>|<span data-ttu-id="e8c37-157">D</span><span class="sxs-lookup"><span data-stu-id="e8c37-157">D</span></span>|<span data-ttu-id="e8c37-158">Saprfc.ini ファイルから接続パラメーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e8c37-158">Picks the connection parameters from the saprfc.ini file.</span></span>|  
|<span data-ttu-id="e8c37-159">クライアント (クライアント)</span><span class="sxs-lookup"><span data-stu-id="e8c37-159">Client (CLIENT)</span></span>|<span data-ttu-id="e8c37-160">A、B、D</span><span class="sxs-lookup"><span data-stu-id="e8c37-160">A,B,D</span></span>|<span data-ttu-id="e8c37-161">SAP クライアント番号</span><span class="sxs-lookup"><span data-stu-id="e8c37-161">The SAP client number</span></span>|  
|<span data-ttu-id="e8c37-162">言語 (Lang)</span><span class="sxs-lookup"><span data-stu-id="e8c37-162">Language (Lang)</span></span>|<span data-ttu-id="e8c37-163">A、B、D</span><span class="sxs-lookup"><span data-stu-id="e8c37-163">A,B,D</span></span>|<span data-ttu-id="e8c37-164">言語</span><span class="sxs-lookup"><span data-stu-id="e8c37-164">Language</span></span>|  
|<span data-ttu-id="e8c37-165">パスワード (PASSWD)</span><span class="sxs-lookup"><span data-stu-id="e8c37-165">Password (PASSWD)</span></span>|<span data-ttu-id="e8c37-166">A、B、D</span><span class="sxs-lookup"><span data-stu-id="e8c37-166">A,B,D</span></span>|<span data-ttu-id="e8c37-167">SAP ユーザー パスワード</span><span class="sxs-lookup"><span data-stu-id="e8c37-167">The SAP user password</span></span>|  
|<span data-ttu-id="e8c37-168">ユーザー名 (ユーザー)</span><span class="sxs-lookup"><span data-stu-id="e8c37-168">Username (USER)</span></span>|<span data-ttu-id="e8c37-169">A、B、D</span><span class="sxs-lookup"><span data-stu-id="e8c37-169">A,B,D</span></span>|<span data-ttu-id="e8c37-170">SAP システムに接続するユーザー名</span><span class="sxs-lookup"><span data-stu-id="e8c37-170">The user name to connect to an SAP system</span></span>|  
|<span data-ttu-id="e8c37-171">SAP GUI (AbapDebug) のデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e8c37-171">Enable SAP GUI debugging (AbapDebug)</span></span>|<span data-ttu-id="e8c37-172">A、B、D</span><span class="sxs-lookup"><span data-stu-id="e8c37-172">A,B,D</span></span>|<span data-ttu-id="e8c37-173">省略可能なパラメーターを指定するかどうかからデバッグを ABAP[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]が有効になって、アダプターは、SAP GUI を使用して、デバッグ用かどうかとします。</span><span class="sxs-lookup"><span data-stu-id="e8c37-173">Optional parameter that specifies whether ABAP debugging from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] is enabled and whether the adapter uses the SAP GUI for debugging.</span></span> <span data-ttu-id="e8c37-174">値を指定できます True または False です。True の場合、ABAP デバッグを有効にされ、SAP GUI が開かれます。</span><span class="sxs-lookup"><span data-stu-id="e8c37-174">The value can be True or False; if True, ABAP debugging is enabled and the SAP GUI is opened.</span></span> <span data-ttu-id="e8c37-175">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="e8c37-175">The default is False.</span></span>|  
|<span data-ttu-id="e8c37-176">トレースの RFC SDK(RfcSdkTrace)</span><span class="sxs-lookup"><span data-stu-id="e8c37-176">Trace RFC SDK(RfcSdkTrace)</span></span>|<span data-ttu-id="e8c37-177">A、B、D</span><span class="sxs-lookup"><span data-stu-id="e8c37-177">A,B,D</span></span>|<span data-ttu-id="e8c37-178">RFC ライブラリ トレースが有効になっているかどうかを示す省略可能なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="e8c37-178">Optional parameter that specifies whether RFC library tracing is enabled.</span></span> <span data-ttu-id="e8c37-179">値を指定できます True または False です。True の場合は、RFC ライブラリ トレースが有効にします。</span><span class="sxs-lookup"><span data-stu-id="e8c37-179">The value can be True or False; if True, RFC Library tracing is enabled.</span></span> <span data-ttu-id="e8c37-180">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="e8c37-180">The default is False.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e8c37-181">[プロパティ] 列では、かっこ内で提供される値は、プログラミング ソリューションを通じて接続 URI を提供する際に指定する必要があります接続のプロパティの名前です。</span><span class="sxs-lookup"><span data-stu-id="e8c37-181">The values provided within parentheses in the Property column are the name of the connection properties that must be specified while providing the connection URI through a programming solution.</span></span> <span data-ttu-id="e8c37-182">ただし、ADO インターフェイスを使用して、DDEX プラグインまたは SQL Server インポートおよびエクスポート ウィザードを使用している場合は、接続のプロパティがフレンドリ名として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8c37-182">However, if you are using the DDEX plug-in or SQL Server Import and Export wizard to use the ADO interface, the connection properties are listed as friendly names.</span></span>  
  
## <a name="example-connection-string-for-type-a"></a><span data-ttu-id="e8c37-183">型の接続文字列の例 A</span><span class="sxs-lookup"><span data-stu-id="e8c37-183">Example Connection String for TYPE A</span></span>  
 <span data-ttu-id="e8c37-184">タイプ A の接続文字列の例は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="e8c37-184">An example connection string for TYPE A would look like:</span></span>  
  
```  
TYPE=A; ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
> [!NOTE]
>  <span data-ttu-id="e8c37-185">既定では、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]常に考慮する種類 a への接続文字列</span><span class="sxs-lookup"><span data-stu-id="e8c37-185">By default the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] always considers the connection string to be of TYPE A.</span></span>  
  
## <a name="example-connection-string-for-type-b"></a><span data-ttu-id="e8c37-186">B の種類用の接続文字列の例</span><span class="sxs-lookup"><span data-stu-id="e8c37-186">Example Connection String for TYPE B</span></span>  
 <span data-ttu-id="e8c37-187">タイプ B の接続文字列の例は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="e8c37-187">An example connection string for TYPE B would look like:</span></span>  
  
```  
TYPE=B; R3NAME=NAME1; GROUP=ADAPTER; MSHOST=MSSERVER; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
## <a name="example-connection-string-for-type-d"></a><span data-ttu-id="e8c37-188">種類 D の接続文字列の例</span><span class="sxs-lookup"><span data-stu-id="e8c37-188">Example Connection String for TYPE D</span></span>  
 <span data-ttu-id="e8c37-189">種類 D の接続文字列の例は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="e8c37-189">An example connection string for TYPE D would look like:</span></span>  
  
```  
TYPE=D; DEST=TESTSAPSRV; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
 <span data-ttu-id="e8c37-190">Saprfc.ini ファイルの例のようになります。</span><span class="sxs-lookup"><span data-stu-id="e8c37-190">A sample saprfc.ini file resembles:</span></span>  
  
```  
DEST=TESTSAPSRV  
TYPE=A  
ASHOST=ADAPSAP47  
SYSNR=00  
```  
  
 <span data-ttu-id="e8c37-191">Saprfc.ini ファイルの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=91457](http://go.microsoft.com/fwlink/?LinkId=91457)です。</span><span class="sxs-lookup"><span data-stu-id="e8c37-191">For more information about the saprfc.ini file, see [http://go.microsoft.com/fwlink/?LinkId=91457](http://go.microsoft.com/fwlink/?LinkId=91457).</span></span>  
  
 <span data-ttu-id="e8c37-192">すべての 3 つの接続の種類のパスワードは、二重引用符を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e8c37-192">The password for all three connection types must not contain double quotation marks.</span></span> <span data-ttu-id="e8c37-193">ただし、パスワードの特殊文字が含まれている場合、パスワードを二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8c37-193">However, if the password contains any other special characters, the password must be enclosed within double quotation marks.</span></span> <span data-ttu-id="e8c37-194">例:</span><span class="sxs-lookup"><span data-stu-id="e8c37-194">For example:</span></span>  
  
```  
ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=",@/:;_ \\";  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8c37-195">1 つだけの接続の種類の A、B、または D. の接続パラメーターを指定する必要があります。たとえば、接続文字列で、アプリケーション サーバーのホストを指定する場合必要がありますいないを指定するメッセージ サーバーのホスト名または、R3NAME。</span><span class="sxs-lookup"><span data-stu-id="e8c37-195">You must specify the connection parameters for only one connection TYPE A, B, or D. For example, if you specify the Application Server Host in the connection string, you must not specify a Message Server Host name or the R3NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c37-196">参照</span><span class="sxs-lookup"><span data-stu-id="e8c37-196">See Also</span></span>  
 [<span data-ttu-id="e8c37-197">使用して、.NET Framework Data Provider 用 mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="e8c37-197">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)