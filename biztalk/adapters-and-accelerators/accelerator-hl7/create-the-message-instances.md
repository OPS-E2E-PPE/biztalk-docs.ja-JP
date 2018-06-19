---
title: メッセージ インスタンスを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d75cb744-99a0-44bc-9a84-d4f8f66fd97e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfd39e1da4e8c730e2ca1c663a5844355ac9cd08
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960216"
---
# <a name="create-the-message-instances"></a><span data-ttu-id="3b395-102">メッセージ インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b395-102">Create the Message Instances</span></span>
<span data-ttu-id="3b395-103">ADT^A03.txt メッセージ ファイルを作成して、バッチ処理のチュートリアルを実行するときに使用する必要があるメッセージ インスタンスを作成するのには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b395-103">Use the following procedures to create the ADT^A03.txt message file, and to create the message instances that you will need to use when you run the Batching tutorial.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b395-104">をメモ帳でこれらのメッセージを作成する場合は、キャリッジ リターンの次の最後の行を削除します。</span><span class="sxs-lookup"><span data-stu-id="3b395-104">When creating these messages in Notepad, delete the carriage return following the last line.</span></span>  
  
### <a name="to-create-the-fragmented-batch-message-instance-text-file"></a><span data-ttu-id="3b395-105">断片化されたバッチのメッセージ インスタンスのテキスト ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="3b395-105">To create the fragmented batch message instance text file</span></span>  
  
1.  <span data-ttu-id="3b395-106">メモ帳を開きます。</span><span class="sxs-lookup"><span data-stu-id="3b395-106">Open Notepad.</span></span>  
  
2.  <span data-ttu-id="3b395-107">次のテキストをメモ帳にコピーします。</span><span class="sxs-lookup"><span data-stu-id="3b395-107">Copy the following text into Notepad:</span></span>  
  
    ```  
    FHS|^~\&|Tutorial_BatchSource|FileSendingFacility|Tutorial_BatchParty|FileReceivingFacility|20040215115056.2222-0800  
    BHS|^~\&|Tutorial_BatchSource|BatchSendingFacility|Tutorial_BatchParty|BatchReceivingFacility|20040215115056.2222-0800  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000001|P|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000002|T|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|DOE^JOHN||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|String^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^JDL&test&DNS^test^test^test^test^test||||004777^DOE^JANE^A.|||SUR||||2|A0  
    BTS|2|Batch,MessageCount,Comment,Totals|2  
    FTS|1|File,BatchCount,TrailerComment  
    ```  
  
3.  <span data-ttu-id="3b395-108">ファイルに保存**FragmentedInboundBatch.txt**で、 \<*ドライブ*:\>\Batching Tutorial\Instances フォルダー、および終値のメモ帳です。</span><span class="sxs-lookup"><span data-stu-id="3b395-108">Save the file as **FragmentedInboundBatch.txt** in the \<*drive*:\>\Batching Tutorial\Instances folder, and then close Notepad.</span></span>  
  
### <a name="to-create-the-batch-inbatch-out-message-instance-text-file"></a><span data-ttu-id="3b395-109">内のバッチの作成/メッセージ インスタンスのテキスト ファイルをバッチ処理するには</span><span class="sxs-lookup"><span data-stu-id="3b395-109">To create the batch in/batch out message instance text file</span></span>  
  
1.  <span data-ttu-id="3b395-110">メモ帳を開きます。</span><span class="sxs-lookup"><span data-stu-id="3b395-110">Open Notepad.</span></span>  
  
2.  <span data-ttu-id="3b395-111">次のテキストをメモ帳にコピーします。</span><span class="sxs-lookup"><span data-stu-id="3b395-111">Copy the following text into Notepad:</span></span>  
  
    ```  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000001|P|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000002|T|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|DOE^JOHN||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|String^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^JDL&test&DNS^test^test^test^test^test||||004777^DOE^JANE^A.|||SUR||||2|A0  
    ```  
  
3.  <span data-ttu-id="3b395-112">ファイルに保存**BatchInBatchOut.txt**で、 \<*ドライブ*:\>\Batching Tutorial\Instances フォルダー、および終値のメモ帳です。</span><span class="sxs-lookup"><span data-stu-id="3b395-112">Save the file as **BatchInBatchOut.txt** in the \<*drive*:\>\Batching Tutorial\Instances folder, and then close Notepad.</span></span>  
  
### <a name="to-create-the-create-batch-message-instance-text-files"></a><span data-ttu-id="3b395-113">テキスト ファイルを作成するバッチのメッセージ インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="3b395-113">To create the create batch message instance text files</span></span>  
  
1.  <span data-ttu-id="3b395-114">メモ帳を開きます。</span><span class="sxs-lookup"><span data-stu-id="3b395-114">Open Notepad.</span></span>  
  
2.  <span data-ttu-id="3b395-115">次のテキストをメモ帳にコピーします。</span><span class="sxs-lookup"><span data-stu-id="3b395-115">Copy the following text into Notepad:</span></span>  
  
    ```  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|Tutorial_BatchDest|XYZ_HOSPITAL|20040215115056||ADT^A03|Msg01|P|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
    ```  
  
3.  <span data-ttu-id="3b395-116">ファイルに保存**CreateBatchMessage1.txt**で、 \<*ドライブ*:\>\Batching Tutorial\Instances フォルダー、および終値のメモ帳です。</span><span class="sxs-lookup"><span data-stu-id="3b395-116">Save the file as **CreateBatchMessage1.txt** in the \<*drive*:\>\Batching Tutorial\Instances folder, and then close Notepad.</span></span>  
  
4.  <span data-ttu-id="3b395-117">メモ帳の新しいインスタンスに、次のテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3b395-117">Copy the following text into a new instance of Notepad:</span></span>  
  
    ```  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|Tutorial_BatchDest|XYZ_HOSPITAL|20040215115056||ADT^A03|Msg02|T|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|DOE^JOHN||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|String^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^JDL&test&DNS^test^test^test^test^test||||004777^DOE^JANE^A.|||SUR||||2|A0  
    ```  
  
5.  <span data-ttu-id="3b395-118">ファイルに保存**CreateBatchMessage2.txt**で、 \<*ドライブ*:\>\Batching Tutorial\Instances フォルダー、および終値のメモ帳です。</span><span class="sxs-lookup"><span data-stu-id="3b395-118">Save the file as **CreateBatchMessage2.txt** in the \<*drive*:\>\Batching Tutorial\Instances folder, and then close Notepad.</span></span>  
  
 <span data-ttu-id="3b395-119">進みます[パート 1: 受信バッチのシナリオを断片化](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="3b395-119">Proceed to [Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md).</span></span>