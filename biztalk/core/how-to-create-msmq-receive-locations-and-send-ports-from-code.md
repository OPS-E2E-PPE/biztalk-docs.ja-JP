---
title: MSMQ を作成するコードからの受信場所と送信ポート |Microsoft Docs
description: プログラムで作成する MSMQ 受信場所と、BizTalk Server での送信ポート
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ebb4119-deeb-4287-aa65-7597ff0cc435
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f367680408f208d5d7a93ef45e925ddfc1893ba5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989763"
---
# <a name="create-msmq-receive-locations-and-send-ports-programmatically"></a><span data-ttu-id="7b96e-103">MSMQ 受信場所と送信ポートをプログラムで作成します。</span><span class="sxs-lookup"><span data-stu-id="7b96e-103">Create MSMQ Receive Locations and Send Ports programmatically</span></span>
<span data-ttu-id="7b96e-104">このトピックでは、WMI を使用して MSMQ アダプタのポートまたは場所を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b96e-104">This topic explains how to use WMI to create a port or location for the MSMQ adapter.</span></span>  
  
 <span data-ttu-id="7b96e-105">詳細については、**日時スケジュール構成を使用して WMI の受信場所を作成する**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b96e-105">For more information, see **Creating a Receive Location with a Datetime Schedule Configuration Using WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="setting-property-values"></a><span data-ttu-id="7b96e-106">プロパティ値の設定</span><span class="sxs-lookup"><span data-stu-id="7b96e-106">Setting Property Values</span></span>  
 <span data-ttu-id="7b96e-107">ポートまたは場所を作成するプロセスは常に同じです。</span><span class="sxs-lookup"><span data-stu-id="7b96e-107">The process of creating a port or location is always the same:</span></span>  
  
1. <span data-ttu-id="7b96e-108">適切な種類のオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7b96e-108">Create an object of the right type.</span></span>  
  
2. <span data-ttu-id="7b96e-109">オブジェクトのプロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7b96e-109">Set the value of properties on the object.</span></span>  
  
3. <span data-ttu-id="7b96e-110">オブジェクト値をデータベースにコミットします。</span><span class="sxs-lookup"><span data-stu-id="7b96e-110">Commit the object values to the database.</span></span>  
  
   <span data-ttu-id="7b96e-111">すべてのアダプターは、特定のプロパティをなどある**HostName**、共通します。</span><span class="sxs-lookup"><span data-stu-id="7b96e-111">All adapters have certain properties, such as **HostName**, in common.</span></span> <span data-ttu-id="7b96e-112">これらの共通のプロパティを、オブジェクトに直接割り当てることで設定します。</span><span class="sxs-lookup"><span data-stu-id="7b96e-112">You set these common properties by directly assigning them to the object.</span></span> <span data-ttu-id="7b96e-113">次の C# コードは通常の場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="7b96e-113">The following C# code shows a typical case:</span></span>  
  
```  
objReceiveLocation["HostName"] = "BizTalkServerApplication";  
```  
  
 <span data-ttu-id="7b96e-114">一部のアダプタでは共有されていないプロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7b96e-114">You assign values to properties that not all adapters share.</span></span> <span data-ttu-id="7b96e-115">文字列で XML ドキュメントを作成し、その文字列を CustomCfg プロパティに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7b96e-115">You create an XML document in a string and assign that string to the CustomCfg property.</span></span> <span data-ttu-id="7b96e-116">次の C# コードは、通常の場合の FILE アダプタを示しています。</span><span class="sxs-lookup"><span data-stu-id="7b96e-116">The following C# code shows a typical case for a FILE adapter:</span></span>  
  
```  
objReceiveLocation["CustomCfg"] =   
        @"<CustomProps>"  
        + @"<BatchSize>20</BatchSize>"  
        + @"<FileMask>*.xml</FileMask>"  
        + @"<FileNetFailRetryCount>5</FileNetFailRetryCount>"  
        + @"<FileNetFailRetryInt>5</FileNetFailRetryInt>"  
        + @"</CustomProps>";  
```  
  
 <span data-ttu-id="7b96e-117">CustomProps 要素のタグの名前は、アダプタがプロパティに使用する内部名です。</span><span class="sxs-lookup"><span data-stu-id="7b96e-117">The names of the tags in the CustomProps element are the internal names that the adapter uses for the properties.</span></span>  
  
 <span data-ttu-id="7b96e-118">MSMQ アダプタには、CustomProps タグ内に 1 つのタグ (AdapterConfig) があります。</span><span class="sxs-lookup"><span data-stu-id="7b96e-118">The MSMQ adapter has a single tag, AdapterConfig, inside the CustomProps tag.</span></span> <span data-ttu-id="7b96e-119">AdapterConfig タグには、Config タグで囲まれたカスタム プロパティ値の XML タグの文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b96e-119">The AdapterConfig tag contains a string of XML tags for the custom property values enclosed in a Config tag.</span></span> <span data-ttu-id="7b96e-120">ただし、タグがエンコードされます:"&lt;「置換」\<「と」&gt;「置換」\>"。</span><span class="sxs-lookup"><span data-stu-id="7b96e-120">However, the tags are encoded: "&lt;" replaces "\<" and "&gt;" replaces "\>".</span></span> <span data-ttu-id="7b96e-121">たとえば、MSMQ プロパティのアダプタのサブセットの XML は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7b96e-121">For example, the XML for a subset of the adapter for MSMQ properties might appear as follows:</span></span>  
  
```  
<Config>  
    <batchSize>40</batchSize>  
</Config>  
```  
  
 <span data-ttu-id="7b96e-122">なお、 **vt**属性は使用されません。</span><span class="sxs-lookup"><span data-stu-id="7b96e-122">Notice that the **vt** attribute is not used.</span></span> <span data-ttu-id="7b96e-123">割り当てられた文字列、 **CustomCfg**プロパティは次のようにエンコードした後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b96e-123">The string assigned to the **CustomCfg** property appears as follows after encoding:</span></span>  
  
```  
<CustomProps><AdapterConfig vt="8"><Config><batchSize>40</batchSize></Config></AdapterConfig></CustomProps>  
```  
  
## <a name="custom-property-names"></a><span data-ttu-id="7b96e-124">カスタム プロパティ名</span><span class="sxs-lookup"><span data-stu-id="7b96e-124">Custom Property Names</span></span>  
 <span data-ttu-id="7b96e-125">次の表に、MSMQ アダプターの内部名**送信**カスタム プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7b96e-125">The following table describes the internal names of the MSMQ adapter **Send** custom properties.</span></span>  
  
|<span data-ttu-id="7b96e-126">**カスタム プロパティの名前を送信します。**</span><span class="sxs-lookup"><span data-stu-id="7b96e-126">**Send custom property name**</span></span>|<span data-ttu-id="7b96e-127">**表示名**</span><span class="sxs-lookup"><span data-stu-id="7b96e-127">**Display name**</span></span>|  
|-----------------------------------|----------------------|  
|<span data-ttu-id="7b96e-128">acknowledgeType</span><span class="sxs-lookup"><span data-stu-id="7b96e-128">acknowledgeType</span></span>|<span data-ttu-id="7b96e-129">受信確認の種類</span><span class="sxs-lookup"><span data-stu-id="7b96e-129">Acknowledgement Type</span></span>|  
|<span data-ttu-id="7b96e-130">administrationQueue</span><span class="sxs-lookup"><span data-stu-id="7b96e-130">administrationQueue</span></span>|<span data-ttu-id="7b96e-131">[管理キュー]</span><span class="sxs-lookup"><span data-stu-id="7b96e-131">Administration Queue</span></span>|  
|<span data-ttu-id="7b96e-132">証明書 (certificate)</span><span class="sxs-lookup"><span data-stu-id="7b96e-132">certificate</span></span>|<span data-ttu-id="7b96e-133">証明書の拇印</span><span class="sxs-lookup"><span data-stu-id="7b96e-133">Certificate Thumbprint</span></span>|  
|<span data-ttu-id="7b96e-134">encryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="7b96e-134">encryptionAlgorithm</span></span>|<span data-ttu-id="7b96e-135">暗号化アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="7b96e-135">Encryption Algorithm</span></span>|  
|<span data-ttu-id="7b96e-136">maximumMessageSize</span><span class="sxs-lookup"><span data-stu-id="7b96e-136">maximumMessageSize</span></span>|<span data-ttu-id="7b96e-137">[メッセージの最大サイズ (KB)]</span><span class="sxs-lookup"><span data-stu-id="7b96e-137">Maximum Message Size (in KB)</span></span>|  
|<span data-ttu-id="7b96e-138">password</span><span class="sxs-lookup"><span data-stu-id="7b96e-138">password</span></span>|<span data-ttu-id="7b96e-139">パスワード</span><span class="sxs-lookup"><span data-stu-id="7b96e-139">Password</span></span>|  
|<span data-ttu-id="7b96e-140">priority</span><span class="sxs-lookup"><span data-stu-id="7b96e-140">priority</span></span>|<span data-ttu-id="7b96e-141">メッセージの優先度</span><span class="sxs-lookup"><span data-stu-id="7b96e-141">Message Priority</span></span>|  
|<span data-ttu-id="7b96e-142">queue</span><span class="sxs-lookup"><span data-stu-id="7b96e-142">queue</span></span>|<span data-ttu-id="7b96e-143">送信先キュー</span><span class="sxs-lookup"><span data-stu-id="7b96e-143">Destination Queue</span></span>|  
|<span data-ttu-id="7b96e-144">recoverable</span><span class="sxs-lookup"><span data-stu-id="7b96e-144">recoverable</span></span>|<span data-ttu-id="7b96e-145">回復可能</span><span class="sxs-lookup"><span data-stu-id="7b96e-145">Recoverable</span></span>|  
|<span data-ttu-id="7b96e-146">segmentationSupport</span><span class="sxs-lookup"><span data-stu-id="7b96e-146">segmentationSupport</span></span>|<span data-ttu-id="7b96e-147">[セグメント化のサポート]</span><span class="sxs-lookup"><span data-stu-id="7b96e-147">Support Segmentation</span></span>|  
|<span data-ttu-id="7b96e-148">sendBatchSize</span><span class="sxs-lookup"><span data-stu-id="7b96e-148">sendBatchSize</span></span>|<span data-ttu-id="7b96e-149">バッチ サイズ</span><span class="sxs-lookup"><span data-stu-id="7b96e-149">Batch Size</span></span>|  
|<span data-ttu-id="7b96e-150">sendQueueName</span><span class="sxs-lookup"><span data-stu-id="7b96e-150">sendQueueName</span></span>|<span data-ttu-id="7b96e-151">送信先キュー</span><span class="sxs-lookup"><span data-stu-id="7b96e-151">Destination Queue</span></span>|  
|<span data-ttu-id="7b96e-152">timeOut</span><span class="sxs-lookup"><span data-stu-id="7b96e-152">timeOut</span></span>|<span data-ttu-id="7b96e-153">Timeout</span><span class="sxs-lookup"><span data-stu-id="7b96e-153">Timeout</span></span>|  
|<span data-ttu-id="7b96e-154">timeOutUnits</span><span class="sxs-lookup"><span data-stu-id="7b96e-154">timeOutUnits</span></span>|<span data-ttu-id="7b96e-155">タイムアウトの単位</span><span class="sxs-lookup"><span data-stu-id="7b96e-155">Timeout Unit</span></span>|  
|<span data-ttu-id="7b96e-156">transactional</span><span class="sxs-lookup"><span data-stu-id="7b96e-156">transactional</span></span>|<span data-ttu-id="7b96e-157">トランザクション</span><span class="sxs-lookup"><span data-stu-id="7b96e-157">Transactional</span></span>|  
|<span data-ttu-id="7b96e-158">useAuthentication</span><span class="sxs-lookup"><span data-stu-id="7b96e-158">useAuthentication</span></span>|<span data-ttu-id="7b96e-159">[認証の使用]</span><span class="sxs-lookup"><span data-stu-id="7b96e-159">Use Authentication</span></span>|  
|<span data-ttu-id="7b96e-160">useDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="7b96e-160">useDeadLetterQueue</span></span>|<span data-ttu-id="7b96e-161">[配信不能メッセージ キューの使用]</span><span class="sxs-lookup"><span data-stu-id="7b96e-161">Use Dead Letter Queue</span></span>|  
|<span data-ttu-id="7b96e-162">useJournalQueue</span><span class="sxs-lookup"><span data-stu-id="7b96e-162">useJournalQueue</span></span>|<span data-ttu-id="7b96e-163">[ジャーナル キューの使用]</span><span class="sxs-lookup"><span data-stu-id="7b96e-163">Use Journal Queue</span></span>|  
|<span data-ttu-id="7b96e-164">userName</span><span class="sxs-lookup"><span data-stu-id="7b96e-164">userName</span></span>|<span data-ttu-id="7b96e-165">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="7b96e-165">User Name</span></span>|  
  
 <span data-ttu-id="7b96e-166">次の表に、MSMQ アダプターの内部名**受信**カスタム プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7b96e-166">The following table describes the internal names of the MSMQ adapter **Receive** custom properties.</span></span>  
  
|<span data-ttu-id="7b96e-167">**カスタム プロパティの名前が表示されます。**</span><span class="sxs-lookup"><span data-stu-id="7b96e-167">**Receive custom property name**</span></span>|<span data-ttu-id="7b96e-168">**表示名**</span><span class="sxs-lookup"><span data-stu-id="7b96e-168">**Display name**</span></span>|  
|--------------------------------------|----------------------|  
|<span data-ttu-id="7b96e-169">batchSize</span><span class="sxs-lookup"><span data-stu-id="7b96e-169">batchSize</span></span>|<span data-ttu-id="7b96e-170">バッチ サイズ</span><span class="sxs-lookup"><span data-stu-id="7b96e-170">Batch Size</span></span>|  
|<span data-ttu-id="7b96e-171">パスワード</span><span class="sxs-lookup"><span data-stu-id="7b96e-171">Password</span></span>|<span data-ttu-id="7b96e-172">パスワード</span><span class="sxs-lookup"><span data-stu-id="7b96e-172">Password</span></span>|  
|<span data-ttu-id="7b96e-173">キュー</span><span class="sxs-lookup"><span data-stu-id="7b96e-173">Queue</span></span>|<span data-ttu-id="7b96e-174">キュー</span><span class="sxs-lookup"><span data-stu-id="7b96e-174">Queue</span></span>|  
|<span data-ttu-id="7b96e-175">serialProcessing</span><span class="sxs-lookup"><span data-stu-id="7b96e-175">serialProcessing</span></span>|<span data-ttu-id="7b96e-176">[順次処理]</span><span class="sxs-lookup"><span data-stu-id="7b96e-176">Serial Processing</span></span>|  
|<span data-ttu-id="7b96e-177">トランザクション</span><span class="sxs-lookup"><span data-stu-id="7b96e-177">Transactional</span></span>|<span data-ttu-id="7b96e-178">トランザクション</span><span class="sxs-lookup"><span data-stu-id="7b96e-178">Transactional</span></span>|  
|<span data-ttu-id="7b96e-179">userName</span><span class="sxs-lookup"><span data-stu-id="7b96e-179">userName</span></span>|<span data-ttu-id="7b96e-180">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="7b96e-180">User Name</span></span>|  
  
## <a name="sample-code"></a><span data-ttu-id="7b96e-181">サンプル コード</span><span class="sxs-lookup"><span data-stu-id="7b96e-181">Sample Code</span></span>  
 <span data-ttu-id="7b96e-182">次の C# プログラムは、MSMQ アダプタの単一の受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="7b96e-182">The following C# program creates a single receive location for the MSMQ adapter.</span></span> <span data-ttu-id="7b96e-183">受信ポート ReceivePort1 が存在し、ヘルパ関数を使用してカスタム プロパティをエンコードおよび書式設定することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7b96e-183">It assumes that the receive port, ReceivePort1, exists and uses a helper function to encode and format the custom properties.</span></span>  
  
```  
using System;  
using System.Management;  
using System.Text;  
  
namespace CreateReceive  
{  
    ///   
    /// Program to create a receive location.  
    ///   
    class CreateReceive  
    {  
        /// The main entry point for the application.  
  
        [STAThread]  
        static void Main()  
        {  
            // Custom properties & values  
            string cfg =   
                    @"<queue>FORMATNAME:DIRECT=OS:MYMACHINE02\PRIVATE$\QUEUE2</queue>"  
                    + @"<batchSize>40</batchSize>"  
                    + @"<transactional>true</transactional>"  
                    + @"<serialProcessing>false</serialProcessing>";  
  
            CreateReceiveLocation (  
                    "Code Created Location",  
                    "ReceivePort1",  
                    "MSMQ",  
                    "BizTalkServerApplication",  
                    EncodeCustomProps(cfg),  // Encode the custom props  
                    "Microsoft.BizTalk.DefaultPipelines.PassThruReceive,"   
                            + " Microsoft.BizTalk.DefaultPipelines,"   
                            + " Version=3.0.1.0, Culture=neutral,"   
                            + " PublicKeyToken=31bf3856ad364e35",  
                    @"FORMATNAME:DIRECT=OS:MYMACHINE\PRIVATE$\QUEUE2"  
                );  
  
        }  
  
        static string EncodeCustomProps (string cp) {  
  
            // Enclose the properties and values in a Config> tag.  
            StringBuilder tmp = new StringBuilder( @"<Config>" + cp + @"</Config>");  
  
            // Encode the string  
            tmp = tmp.Replace("<","<");  
            tmp = tmp.Replace(">",">");  
  
            return (  
                // Enclose the encoded string with necessary tags  
                "<CustomProps><AdapterConfig vt=\"8\">"  
                + tmp.ToString()   
                + "</AdapterConfig></CustomProps>");  
  
        }  
  
        static void CreateReceiveLocation (  
            string name,            // Location name  
            string port,            // Receive port, already exists  
            string adapterName,     // The transport type  
            string hostName,        // BTS host  
            string customCfg,       // Encoded custom properties  
            string pipeline,        // Full specification of pipeline  
            string inboundTransport)// Inbound transport url  
        {  
            try   
            {  
                // Create options to store options in management object  
                PutOptions options = new PutOptions();  
                options.Type = PutType.CreateOnly;  
  
                // Create a management object  
                // Get the class  
                ManagementClass objReceiveLocationClass =   
                           new ManagementClass(  
                               "root\\MicrosoftBizTalkServer",   
                               "MSBTS_ReceiveLocation",   
                               null);  
                // Create an instance of the member of the class  
                ManagementObject objReceiveLocation =  
                          objReceiveLocationClass.CreateInstance();  
  
                // Fill in the properties  
                objReceiveLocation["Name"] = name;  
                objReceiveLocation["ReceivePortName"] = port;  
                objReceiveLocation["AdapterName"] = adapterName;  
                objReceiveLocation["HostName"] = hostName;  
                objReceiveLocation["PipelineName"] = pipeline;  
                objReceiveLocation["CustomCfg"] = customCfg;  
                objReceiveLocation["IsDisabled"] = true;  
                objReceiveLocation["InBoundTransportURL"] = inboundTransport;  
  
                // Put the options -- creates the receive location  
                objReceiveLocation.Put(options);  
            }  
            catch (Exception excep)  
            {  
                System.Console.WriteLine("Create Receive Location ({0}) failed - {1}",  
                                                name, excep.Message);  
            }  
        }  
    }  
}  
```