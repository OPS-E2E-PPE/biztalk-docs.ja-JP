---
title: ソリューションのインストルメント化します。API の使用方法をステップ バイ ステップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9e027ab-1927-4905-8970-8061ac55d591
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c9d3ecd3f479729acd720a61254a6f82c655a0a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382050"
---
# <a name="instrumenting-a-solution-step-by-step-api-usage"></a>ソリューションのインストルメント化します。ステップ バイ ステップの API 使用量
このトピックでは、主要な BAM API クラスを使用してアプリケーションをインストルメント化する方法を説明します。 以下のコードは、定数と、アプリケーションのインストルメント化に必要な最小限のコードを使用して、サンプル コードを単純化したものです。  
  
 次のコード スニペットでは、 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) オブジェクト、具体的には、 [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)を新規に作成する方法を示しています。 このコードでは、最初のパラメーターで BAM プライマリ インポート データベースのデータ ストアへの接続文字列を指定し、2 番目のパラメーターでイベントがデータ ストアに書き込まれる頻度を指定しています。  
  
> [!NOTE]
>  BAM では、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データ ストアへの接続のみがサポートされています。 このサンプルの接続文字列は、接続を確立するために必要な最低限の接続文字列を表しています。 構成によっては、接続文字列で追加のパラメーターを指定する必要があります。  
  
 *FlushThreshold* の値を 0 にすると、イベントが自動的に書き込まれなくなります。この場合、イベントを書き込むには Flush メソッドを呼び出す必要があります。 この値を 1 にすると、イベントは発生するたびに書き込まれます。 1 より大きい値にすると、発生したイベントの数が指定した値になるとイベントが書き込まれます。 この設定は、パフォーマンスの向上に役立ちます。  
  
```  
// Specify the DES connection string.  
const string connBAMPIT =  
   "Integrated Security=SSPI;server=.;database=BAMPrimaryImport";  
// Write the activity update data on every call.  
int flushThreshold = 1;  
// Create a DES instance  
EventStream es =   
   new DirectEventStream(connBAMPIT, flushThreshold);  
```  
  
 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) オブジェクトが作成されたら、アクティビティを開始して、収集されたマイルストーンとデータでアクティビティ テーブルを更新できます。 BAM アクティビティが展開されたときに、BAM プライマリ インポート データベースに 5 つのテーブルが作成されています。 開発プロセスの詳細については、「 [Overview of the BAM Development Process](../core/overview-of-the-bam-development-process.md)」を参照してください。  
  
 [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) メソッドを呼び出すと、bam _ PurchaseOrder_Activity テーブルにレコードが追加されます。 最初のパラメーターには、更新されるアクティビティの名前が含まれています。2 番目のパラメーターには、そのアクティビティの現在のインスタンスの識別子が含まれています。 識別子には任意の文字列を使用できますが、アクティビティのレコードセットで一意である必要があります。  
  
 この時点では、レコードにデータは含まれていません。 [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) メソッドが、キャプチャされたイベント データでレコードを更新します。 ここでも、アクティビティと、そのアクティビティのインスタンスの識別子を指定します。 [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) メソッドには、アクティビティで定義したデータ項目とマイルストーンの名前と値の組を渡します。 たとえば、この例のアクティビティではマイルストーン MS_Received が定義されています。 アクティビティが展開されたときに、このマイルストーンのための列が bam_ PurchaseOrder_Activity テーブルに作成されています。 [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) メソッドの呼び出しで MS_Received と DateTime.UtcNow という名前と値の組を指定して、注文書の受信日でアクティビティを更新します。  
  
```  
// When a purchase order is received, you call the  
// BeginActivity method in the receive application.  
// You can then capture the event data by calling   
// the UpdateActivity method.  
es.BeginActivity ("PurchaseOrder", "PO123");  
es.UpdateActivity ("PurchaseOrder", "PO123",  
                    "MS_Received", DateTime.UtcNow,   
                    "T_Customer", "Joe");  
```  
  
 このサンプルでは 2 番目のアクティビティに継続します。 Continuation の詳細については、「 [Activity Continuation](../core/activity-continuation.md)」を参照してください。  
  
 他のインストルメント アプリケーションが PurchaseOrder アクティビティを更新できるようにするには、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) メソッドの呼び出しを追加します。 この呼び出しでは、他のアプリケーションが関与できるアクティビティ、追跡するアクティビティのインスタンスの識別子、および他のアプリケーションがアクティビティを更新するために使用する継続トークンを指定します。 継続の状態を追跡するために、bam_ PurchaseOrder_continuations テーブルにレコードが書き込まれます。 アクティビティが他のプロセスに継続される場合、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) メソッドが一意の継続トークンで呼び出されるたびにレコードが書き込まれます。  
  
> [!IMPORTANT]
>  継続のシナリオでは、すべてのコード セグメントに [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) メソッドの呼び出しが含まれている必要があります。 そうでないと、ぶら下がり/孤立状態のアクティビティ レコードが生じます。  
>   
>  ただし、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) メソッドがあるのは最初のセグメント (実際のアクティビティ ID を使用するセグメント) だけです。その他のセグメント (それぞれの一意のトークン ID を使用するセグメント) では [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) メソッドを呼び出さないでください。  
  
 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) メソッドが呼び出されると、他のコンポーネントが PurchaseOrder アクティビティを更新できるようになります。その際には、アクティビティ ID の代わりに継続トークンを指定して、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) を使用します。 他のコンポーネントでは、それぞれのタスクが完了したら、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) を継続トークンと共に呼び出して、イベントがこれ以上発生しないことを BAM インフラストラクチャに通知する必要があります。  
  
> [!IMPORTANT]
>  [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) メソッドが呼び出された後に、アクティビティが継続されているプロセスで [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) メソッドが継続トークンと共に呼び出されないと、アクティビティが孤立する可能性があります。  
  
```  
// Continue the activity to the next process that has been  
// instrumented to handle the continuation.  
es.EnableContinuation("PurchaseOrder", “PO123”, “AP123”);  
```  
  
 最後に、アクティビティ名とアクティビティ識別子を指定して [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) メソッドを呼び出して、アクティビティを終了します。 終了されていない継続がなければ、アクティビティが bam_ PurchaseOrder _completed テーブルに移動されます。 継続アクティビティを完了しないとアクティビティが孤立する可能性があります。  
  
```  
// Activity from this segment (PO submission) is completed  
es.EndActivity("PurchaseOrder", “PO123”);  
```  
  
 アクティビティが別のプロセスに継続されると、アクティビティ テーブルを更新する際にアクティビティ名と継続トークン ( [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) メソッドの呼び出しで宣言される) を指定して [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) を呼び出すようにアプリケーションがインストルメント化されます。  
  
> [!NOTE]
>  継続されたアクティビティを処理するプロセスでは、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) メソッドは呼び出しません。 [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) メソッドは、BAM プライマリ インポート データベースのテーブルを作成することによってアクティビティのインスタンスを作成します。 アクティビティの継続先プロセスでは、既に存在するアクティビティのインスタンスを更新します。  
  
```  
// update when the order is approved  
es.UpdateActivity ("PurchaseOrder", “AP123”, "MS_Approved",  
                    DateTime.UtcNow, "T_Product", "Widget");  
  
// update when the product is ready for shipment  
es.UpdateActivity ("PurchaseOrder", “AP123”,  
                   "MS_Ready", DateTime.UtcNow);  
```  
  
 このサンプルのワークフローの一部では、コードで参照が指定されています。この場合の参照は、関連アクティビティという特別な種類の参照です。 関連アクティビティを指定すると、プライマリ アクティビティから、BAM ポータルでそのアクティビティを表示するユーザーにとって関心のある他のアクティビティに、リンクを作成できます。  
  
 [Microsoft.BizTalk.Bam.EventObservation.EventStream.AddRelatedActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.addrelatedactivity.aspx) メソッドを呼び出すと、bam_ PurchaseOrder_ActiveRelationships にレコードが書き込まれて、アクティビティがリンクされます。  
  
```  
// These are shipped in two shipments.  
// Relates the current purchase order   
// instance to two shippings.  
// Note: only one direction  
es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                       "Shipping", “UPS101”);  
es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                       "Shipping", “UPS102”);  
```  
  
 継続されたアクティビティを終了するには、終了する継続の継続トークンを指定して [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) メソッドを呼び出します。 終了されていない継続が他になければ、PurchaseOrder アクティビティが完了済みテーブルに移動されます。  
  
```  
// Activity from this segment (ApprovalProcess) is completed  
es.EndActivity("PurchaseOrder", “AP123”);  
```  
  
## <a name="complete-code-sample"></a>完全なコード例  
  
```  
//---------------------------------------------------------------------  
// File:BAMMinimalSample.cs  
//   
// Summary: Demonstrates how to instrument an application   
//using BAM APIs to track useful information.  
//  
// Sample: BAM Api Sample  
//  
//---------------------------------------------------------------------  
// This file is part of the Microsoft BizTalk Server SDK  
//  
// Copyright (c) Microsoft Corporation. All rights reserved.  
//  
// This source code is intended only as a supplement to Microsoft   
// BizTalk Server release and/or on-line documentation. See   
// these other materials for detailed information regarding Microsoft // code samples.  
//  
// THIS CODE AND INFORMATION ARE PROVIDED "AS IS" WITHOUT WARRANTY OF  
// ANY KIND, WHETHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO // THE IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A   
// PARTICULAR PURPOSE.  
//---------------------------------------------------------------------  
// This sample requires that you add the     
// Microsoft.BizTalk.Bam.EventObservation.dll to the   
// references in the Visual Studio Solution.  
  
using System;  
using System.Text;  
using Microsoft.BizTalk.Bam.EventObservation;  
  
namespace EventStreamSample  
{  
  
    static void Main(string[] args)  
    {  
        //   
  // The following code would appear in a purchase order  
   // receipt application.  
        //  
  
        // Specify the DES connection string.  
        const string connBAMPIT =  
            "Integrated Security=SSPI;server=.;database=BAMPrimaryImport";  
  
        // Write the activity update data on every call.  
        int flushThreshold = 1;  
  
        // Create an instance of the DirectEventStream.  
        EventStream es =   
               new DirectEventStream(connBAMPIT, flushThreshold);  
  
        // When a purchase order is received, you call the  
       // BeginActivity method in the receive application.  
  // You can then capture the event data by calling   
        // the UpdateActivity method.  
        es.BeginActivity ("PurchaseOrder", "PO123");  
        es.UpdateActivity ("PurchaseOrder", "PO123",  
                    "MS_Received", DateTime.UtcNow,   
                    "T_Customer", "Joe");  
  
   // Continue the activity to the next process that has been  
   // instrumented to handle the continuation.  
        es.EnableContinuation("PurchaseOrder", “PO123”, “AP123”);  
  
        // Activity from this segment (PO submission) is completed  
        // end activity is synonymous to IsCompleted = 1  
        es.EndActivity("PurchaseOrder", “PO123”);  
  
        //  
        // The following code would typically appear in a separate   
        // application that monitors the approval process  
        // (ApprovalProcess.exe)  
        //  
  
        // update when the order is approved  
        es.UpdateActivity ("PurchaseOrder", “AP123”, "MS_Approved",  
                            DateTime.UtcNow, "T_Product", "Widget");  
  
        // update when the product is ready for shipment  
        es.UpdateActivity ("PurchaseOrder", “AP123”,  
                            "MS_Ready", DateTime.UtcNow);  
  
        // These are shipped in two shipments.  
        // Relates the current purchase order  
        // instance to two shippings.  
        // Note: only one direction  
        es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                                "Shipping", “UPS101”);  
        es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                                "Shipping", “UPS102”);  
  
        // Activity from this segment (ApprovalProcess) is completed  
        es.EndActivity("PurchaseOrder", “AP123”);  
  
        // In another Shipping application, two shipments with  
            ID’s UPS101 and UPS102 will be created.  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [イベント ストリームを使用した BAM アクティビティを実装します。](../core/implementing-bam-activities-with-event-streams.md)