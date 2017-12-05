---
title: "MSMQ を作成するコードからの受信場所と送信ポート |Microsoft ドキュメント"
description: "MSMQ をプログラムで作成する受信場所と、BizTalk Server での送信ポート"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ebb4119-deeb-4287-aa65-7597ff0cc435
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5f00a0bfe14eeb7d4205973b3fef96e23026616
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="create-msmq-receive-locations-and-send-ports-programmatically"></a>MSMQ 受信場所と送信ポートをプログラムで作成します。
このトピックでは、WMI を使用して MSMQ アダプタのポートまたは場所を作成する方法について説明します。  
  
 詳細については、次を参照してください。**日時スケジュール構成を使用して WMI と受信場所を作成する**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="setting-property-values"></a>プロパティ値の設定  
 ポートまたは場所を作成するプロセスは常に同じです。  
  
1.  適切な種類のオブジェクトを作成します。  
  
2.  オブジェクトのプロパティの値を設定します。  
  
3.  オブジェクト値をデータベースにコミットします。  
  
 すべてのアダプターは、特定のプロパティをなどある**HostName**に共通します。 これらの共通のプロパティを、オブジェクトに直接割り当てることで設定します。 次の C# コードは通常の場合を示しています。  
  
```  
objReceiveLocation["HostName"] = "BizTalkServerApplication";  
```  
  
 一部のアダプタでは共有されていないプロパティに値を割り当てます。 文字列で XML ドキュメントを作成し、その文字列を CustomCfg プロパティに割り当てます。 次の C# コードは、通常の場合の FILE アダプタを示しています。  
  
```  
objReceiveLocation["CustomCfg"] =   
        @"<CustomProps>"  
        + @"<BatchSize>20</BatchSize>"  
        + @"<FileMask>*.xml</FileMask>"  
        + @"<FileNetFailRetryCount>5</FileNetFailRetryCount>"  
        + @"<FileNetFailRetryInt>5</FileNetFailRetryInt>"  
        + @"</CustomProps>";  
```  
  
 CustomProps 要素のタグの名前は、アダプタがプロパティに使用する内部名です。  
  
 MSMQ アダプタには、CustomProps タグ内に 1 つのタグ (AdapterConfig) があります。 AdapterConfig タグには、Config タグで囲まれたカスタム プロパティ値の XML タグの文字列が含まれています。 ただし、タグがエンコードされます:"&lt;「置換」\<「と」&gt;「置換」\>"です。 たとえば、MSMQ プロパティのアダプタのサブセットの XML は次のようになります。  
  
```  
<Config>  
    <batchSize>40</batchSize>  
</Config>  
```  
  
 注意して、 **vt**属性は使用されません。 割り当てられた文字列、 **CustomCfg**エンコード後プロパティは次のように表示されます。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config><batchSize>40</batchSize></Config></AdapterConfig></CustomProps>  
```  
  
## <a name="custom-property-names"></a>カスタム プロパティ名  
 次の表に、MSMQ アダプターの内部名**送信**カスタム プロパティです。  
  
|**カスタム プロパティの名前を送信します。**|**表示名**|  
|-----------------------------------|----------------------|  
|acknowledgeType|受信確認の種類|  
|administrationQueue|[管理キュー]|  
|証明書 (certificate)|証明書の拇印|  
|encryptionAlgorithm|暗号化アルゴリズム|  
|maximumMessageSize|[メッセージの最大サイズ (KB)]|  
|パスワード|Password|  
|priority|メッセージの優先度|  
|queue|送信先キュー|  
|recoverable|回復可能|  
|segmentationSupport|[セグメント化のサポート]|  
|sendBatchSize|バッチ サイズ|  
|sendQueueName|送信先キュー|  
|timeOut|Timeout|  
|timeOutUnits|タイムアウトの単位|  
|transactional|トランザクション|  
|useAuthentication|[認証の使用]|  
|useDeadLetterQueue|[配信不能メッセージ キューの使用]|  
|useJournalQueue|[ジャーナル キューの使用]|  
|userName|[ユーザー名]|  
  
 次の表に、MSMQ アダプターの内部名**受信**カスタム プロパティです。  
  
|**カスタム プロパティの名前が表示されます。**|**表示名**|  
|--------------------------------------|----------------------|  
|batchSize|バッチ サイズ|  
|Password|Password|  
|キュー|キュー|  
|serialProcessing|[順次処理]|  
|トランザクション|トランザクション|  
|userName|[ユーザー名]|  
  
## <a name="sample-code"></a>サンプル コード  
 次の C# プログラムは、MSMQ アダプタの単一の受信場所を作成します。 受信ポート ReceivePort1 が存在し、ヘルパ関数を使用してカスタム プロパティをエンコードおよび書式設定することを前提としています。  
  
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