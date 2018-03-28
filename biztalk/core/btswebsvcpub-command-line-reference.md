---
title: BTSWebSvcPub コマンド ライン リファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e19dd4d-9f2c-4a17-9437-8701e1c274fb
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9993092c0d798ae2d47f614a24da21c3a2df62
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="btswebsvcpub-command-line-reference"></a><span data-ttu-id="09a06-102">BTSWebSvcPub コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="09a06-102">BTSWebSvcPub Command-Line Reference</span></span>
<span data-ttu-id="09a06-103">ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属の BTSWebSvcPub コマンド ライン ツールに関するリファレンス情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="09a06-103">This topic provides reference information for the BTSWebSvcPub command-line tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="09a06-104">BTSWebSvcPub を使用して、次に示すように、Web サービスからオーケストレーションを公開するための Web サービス (.asmx) を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="09a06-104">You can use BTSWebSvcPub to create Web services (.asmx) for publishing orchestrations through Web services as follows:</span></span>  
  
## <a name="usage"></a><span data-ttu-id="09a06-105">使用方法</span><span class="sxs-lookup"><span data-stu-id="09a06-105">Usage</span></span>  
 <span data-ttu-id="09a06-106">**BTSWebSvcPub パス名 [-場所:** *値* **] [の上書き] [-匿名]**</span><span class="sxs-lookup"><span data-stu-id="09a06-106">**BTSWebSvcPub PathName [-Location:** *value* **] [-Overwrite] [-Anonymous]**</span></span>  
  
 <span data-ttu-id="09a06-107">**[-名前:** *値* **] [-名前空間:** *値* **] [-TargetNamespace:** *値* **]**</span><span class="sxs-lookup"><span data-stu-id="09a06-107">**[-Name:** *value* **] [-Namespace:** *value* **] [-TargetNamespace:** *value* **]**</span></span>  
  
 <span data-ttu-id="09a06-108">**[-UnknownHeaders [** *+* **&#124;** *-* **][-SingleSignOn[** *+* **&#124;** *-* **]][-ParameterStyle:** *値* **]**</span><span class="sxs-lookup"><span data-stu-id="09a06-108">**[-UnknownHeaders[** *+* **&#124;** *-* **]] [-SingleSignOn[** *+* **&#124;** *-* **]] [-ParameterStyle:** *value* **]**</span></span>  
  
 <span data-ttu-id="09a06-109">**[-ConformanceClaims:** *値* **] [-ForceRequestResponse:** *値* **] [-受信場所]**</span><span class="sxs-lookup"><span data-stu-id="09a06-109">**[-ConformanceClaims:** *value* **] [-ForceRequestResponse:** *value* **] [-ReceiveLocation]**</span></span>  
  
 <span data-ttu-id="09a06-110">**[-ApplicationName:** *値* **]**</span><span class="sxs-lookup"><span data-stu-id="09a06-110">**[-ApplicationName:** *value* **]**</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="09a06-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="09a06-111">Parameters</span></span>  
  
|<span data-ttu-id="09a06-112">パラメーター</span><span class="sxs-lookup"><span data-stu-id="09a06-112">Parameter</span></span>|<span data-ttu-id="09a06-113">必須</span><span class="sxs-lookup"><span data-stu-id="09a06-113">Required</span></span>|<span data-ttu-id="09a06-114">Description</span><span class="sxs-lookup"><span data-stu-id="09a06-114">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="09a06-115">**パス名**</span><span class="sxs-lookup"><span data-stu-id="09a06-115">**PathName**</span></span>|<span data-ttu-id="09a06-116">可</span><span class="sxs-lookup"><span data-stu-id="09a06-116">Yes</span></span>|<span data-ttu-id="09a06-117">BizTalk アセンブリ (*.dll) または web サービスの説明のパスとファイルの名前 (\*.xml) ファイルです。</span><span class="sxs-lookup"><span data-stu-id="09a06-117">Path and file name of BizTalk assembly (*.dll) or web service description (\*.xml) file.</span></span>|  
|<span data-ttu-id="09a06-118">**-場所**</span><span class="sxs-lookup"><span data-stu-id="09a06-118">**-Location**</span></span>|<span data-ttu-id="09a06-119">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-119">No</span></span>|<span data-ttu-id="09a06-120">公開する場所。</span><span class="sxs-lookup"><span data-stu-id="09a06-120">Location in which to publish.</span></span> <span data-ttu-id="09a06-121">(構文:"http://host[: ポート]/パス")</span><span class="sxs-lookup"><span data-stu-id="09a06-121">(Syntax:"http://host[:port]/path")</span></span>|  
|<span data-ttu-id="09a06-122">**-上書き**</span><span class="sxs-lookup"><span data-stu-id="09a06-122">**-Overwrite**</span></span>|<span data-ttu-id="09a06-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-123">No</span></span>|<span data-ttu-id="09a06-124">指定した場所を上書きします。</span><span class="sxs-lookup"><span data-stu-id="09a06-124">Overwrite specified location.</span></span>|  
|<span data-ttu-id="09a06-125">**匿名**</span><span class="sxs-lookup"><span data-stu-id="09a06-125">**-Anonymous**</span></span>|<span data-ttu-id="09a06-126">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-126">No</span></span>|<span data-ttu-id="09a06-127">Web サービスへの匿名アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="09a06-127">Allow anonymous access to Web service.</span></span>|  
|<span data-ttu-id="09a06-128">**名**</span><span class="sxs-lookup"><span data-stu-id="09a06-128">**-Name**</span></span>|<span data-ttu-id="09a06-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-129">No</span></span>|<span data-ttu-id="09a06-130">Web サービスを含めるソリューションおよびアセンブリ (.sln ファイルおよび .dll ファイル) の名前です。</span><span class="sxs-lookup"><span data-stu-id="09a06-130">Name of the solution and assembly (.sln and .dll files) that will contain the Web service.</span></span>|  
|<span data-ttu-id="09a06-131">**名前空間**</span><span class="sxs-lookup"><span data-stu-id="09a06-131">**-Namespace**</span></span>|<span data-ttu-id="09a06-132">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-132">No</span></span>|<span data-ttu-id="09a06-133">Web サービス コードの既定の名前空間。</span><span class="sxs-lookup"><span data-stu-id="09a06-133">Default namespace for Web service code.</span></span>|  
|<span data-ttu-id="09a06-134">**Targetnamespace**</span><span class="sxs-lookup"><span data-stu-id="09a06-134">**-Targetnamespace**</span></span>|<span data-ttu-id="09a06-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-135">No</span></span>|<span data-ttu-id="09a06-136">Web サービスの対象となる名前空間。</span><span class="sxs-lookup"><span data-stu-id="09a06-136">Target namespace of the Web service.</span></span> <span data-ttu-id="09a06-137">(例:'http://www.northwindtraders.com')</span><span class="sxs-lookup"><span data-stu-id="09a06-137">(Example:'http://www.northwindtraders.com')</span></span>|  
|<span data-ttu-id="09a06-138">**-UnknownHeaders**</span><span class="sxs-lookup"><span data-stu-id="09a06-138">**-UnknownHeaders**</span></span>|<span data-ttu-id="09a06-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-139">No</span></span>|<span data-ttu-id="09a06-140">不明な SOAP ヘッダーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="09a06-140">Support unknown SOAP headers.</span></span>|  
|<span data-ttu-id="09a06-141">**-SinglesSignon**</span><span class="sxs-lookup"><span data-stu-id="09a06-141">**-SinglesSignon**</span></span>|<span data-ttu-id="09a06-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-142">No</span></span>|<span data-ttu-id="09a06-143">SharePoint Portal Server のシングル サインオン SOAP ヘッダーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="09a06-143">Support SharePoint Portal Server Single Sign-On SOAP headers.</span></span>|  
|<span data-ttu-id="09a06-144">**-ParameterStyle**</span><span class="sxs-lookup"><span data-stu-id="09a06-144">**-ParameterStyle**</span></span>|<span data-ttu-id="09a06-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-145">No</span></span>|<span data-ttu-id="09a06-146">メッセージの soapparameterstyle です。"Default"、"Bare"または"Wrapped"です。</span><span class="sxs-lookup"><span data-stu-id="09a06-146">The SoapParameterStyle for messages: "Default", "Bare",or "Wrapped".</span></span>|  
|<span data-ttu-id="09a06-147">**-ConfirmanceClaims**</span><span class="sxs-lookup"><span data-stu-id="09a06-147">**-ConfirmanceClaims**</span></span>|<span data-ttu-id="09a06-148">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-148">No</span></span>|<span data-ttu-id="09a06-149">Web サービスの相互運用性 (WSI) を要求:「なし」または"BasicProfile1_1"です。</span><span class="sxs-lookup"><span data-stu-id="09a06-149">Web services interoperability (WSI) claim: "None" or"BasicProfile1_1".</span></span>|  
|<span data-ttu-id="09a06-150">**-ForceRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="09a06-150">**-ForceRequestResponse**</span></span>|<span data-ttu-id="09a06-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-151">No</span></span>|<span data-ttu-id="09a06-152">一方向の BizTalk 操作を、要求 - 応答 Web メソッドとして公開します。</span><span class="sxs-lookup"><span data-stu-id="09a06-152">Expose one-way BizTalk operations as request-response web methods.</span></span>|  
|<span data-ttu-id="09a06-153">**-受信場所**</span><span class="sxs-lookup"><span data-stu-id="09a06-153">**-ReceiveLocation**</span></span>|<span data-ttu-id="09a06-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-154">No</span></span>|<span data-ttu-id="09a06-155">指定された BizTalk アプリケーションに受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="09a06-155">Create receive locations in the specified BizTalk application.</span></span>|  
|<span data-ttu-id="09a06-156">**-ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="09a06-156">**-ApplicationName**</span></span>|<span data-ttu-id="09a06-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="09a06-157">No</span></span>|<span data-ttu-id="09a06-158">受信場所を作成する BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="09a06-158">Name of the BizTalk application in which to create receive locations.</span></span> <span data-ttu-id="09a06-159">指定しなかった場合、既定の BizTalk アプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="09a06-159">If not specified, the default BizTalk application is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="09a06-160">サンプル</span><span class="sxs-lookup"><span data-stu-id="09a06-160">Sample</span></span>  
 <span data-ttu-id="09a06-161">BTSWebSvcPub.exe "MyAssembly.dll" -Location:http://localhost/MyVdir</span><span class="sxs-lookup"><span data-stu-id="09a06-161">BTSWebSvcPub.exe "MyAssembly.dll" -Location:http://localhost/MyVdir</span></span>  
  
 <span data-ttu-id="09a06-162">-Overwrite</span><span class="sxs-lookup"><span data-stu-id="09a06-162">-Overwrite</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09a06-163">解説</span><span class="sxs-lookup"><span data-stu-id="09a06-163">Remarks</span></span>  
 <span data-ttu-id="09a06-164">パラメータ名では大文字と小文字は区別されません。省略したパラメータ名は使用できます。</span><span class="sxs-lookup"><span data-stu-id="09a06-164">Parameter names are not case sensitive and may be abbreviated.</span></span> <span data-ttu-id="09a06-165">パラメーター値は大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="09a06-165">Parameter values are case sensitive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a06-166">参照</span><span class="sxs-lookup"><span data-stu-id="09a06-166">See Also</span></span>  
 [<span data-ttu-id="09a06-167">BizTalk Web サービス公開ウィザードを使用してオーケストレーションを Web サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="09a06-167">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)