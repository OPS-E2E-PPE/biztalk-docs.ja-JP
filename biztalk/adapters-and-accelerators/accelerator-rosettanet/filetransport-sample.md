---
title: FileTransport サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a32c8cbf-0c17-4237-b2a3-9d21faa13496
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a79759a94b2effd751dd566d62dcdde51395e566
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283719"
---
# <a name="filetransport-sample"></a><span data-ttu-id="c5688-102">FileTransport サンプル</span><span class="sxs-lookup"><span data-stu-id="c5688-102">FileTransport Sample</span></span>
<span data-ttu-id="c5688-103">FileTransport サンプルは Microsoft® を構成する方法を示します[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SQL ポートではなくファイルのポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5688-103">The FileTransport sample demonstrates how to configure Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to use File ports, instead of SQL ports.</span></span> <span data-ttu-id="c5688-104">FileTransport サンプルでは、ファイル転送プロトコル (FTP) を使用して、HTTP ではなく、メッセージの送受信を行います。</span><span class="sxs-lookup"><span data-stu-id="c5688-104">The FileTransport sample uses File Transport Protocol (FTP) to send and receive messages, instead of HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5688-105">このドキュメントは、インストールすることを想定しています[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]内部のテストまたはデモ目的のみ。</span><span class="sxs-lookup"><span data-stu-id="c5688-105">This document assumes that you are installing [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] for internal testing or demonstration purposes only.</span></span> <span data-ttu-id="c5688-106">最小の任意のアカウントを規定したりを設定しません。</span><span class="sxs-lookup"><span data-stu-id="c5688-106">It does not prescribe any minimum-security account or set up.</span></span> <span data-ttu-id="c5688-107">このトピックで、手順全体にわたって、ローカルの管理アクセス許可のあるアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5688-107">You must use an account that has local administrative permissions throughout the procedures in this topic.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="c5688-108">このサンプルは、メッセージの添付ファイルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c5688-108">This sample does not support message attachments.</span></span>  
  
## <a name="filetransport-binding-files"></a><span data-ttu-id="c5688-109">FileTransport バインド ファイル</span><span class="sxs-lookup"><span data-stu-id="c5688-109">FileTransport Binding Files</span></span>  
 <span data-ttu-id="c5688-110">FileTransport サンプルには、2 つのバインド ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5688-110">The FileTransport sample includes two binding files.</span></span> <span data-ttu-id="c5688-111">BTARN のオーケストレーションで使用するためにファイル ポートを設定するには、これらのバインド ファイルの各を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5688-111">You can use each of these binding files to set up File ports for use with a BTARN orchestration.</span></span> <span data-ttu-id="c5688-112">これらのバインド ファイルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet \SDK\FileTransport します。</span><span class="sxs-lookup"><span data-stu-id="c5688-112">These binding files are located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet \SDK\FileTransport.</span></span> <span data-ttu-id="c5688-113">次に示すように、オーケストレーションの設定を表示、送信ポート、受信ポート、および受信場所をメモ帳などのエディターで各バインド ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c5688-113">Open each binding file in an editor like Notepad to see the settings for the orchestration, send port, receive port, and receive location, as listed below.</span></span>  
  
- <span data-ttu-id="c5688-114">PrivateInitiatorusingFileDrops.xml</span><span class="sxs-lookup"><span data-stu-id="c5688-114">PrivateInitiatorusingFileDrops.xml</span></span>  
  
  -   <span data-ttu-id="c5688-115">オーケストレーション:Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess</span><span class="sxs-lookup"><span data-stu-id="c5688-115">Orchestration: Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess</span></span>  
  
  -   <span data-ttu-id="c5688-116">送信ポート。PrivateInitiator_To_File</span><span class="sxs-lookup"><span data-stu-id="c5688-116">Send port: PrivateInitiator_To_File</span></span>  
  
  -   <span data-ttu-id="c5688-117">受信ポート。File_To_PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="c5688-117">Receive port: File_To_PrivateInitiator</span></span>  
  
  -   <span data-ttu-id="c5688-118">受信場所。File_To_PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="c5688-118">Receive location: File_To_PrivateInitiator</span></span>  
  
- <span data-ttu-id="c5688-119">PrivateResponderusingFileDrops.xml</span><span class="sxs-lookup"><span data-stu-id="c5688-119">PrivateResponderusingFileDrops.xml</span></span>  
  
  -   <span data-ttu-id="c5688-120">オーケストレーション:Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess</span><span class="sxs-lookup"><span data-stu-id="c5688-120">Orchestration: Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess</span></span>  
  
  -   <span data-ttu-id="c5688-121">送信ポート。PrivateResponder_To_File</span><span class="sxs-lookup"><span data-stu-id="c5688-121">Send port: PrivateResponder_To_File</span></span>  
  
  -   <span data-ttu-id="c5688-122">受信ポート。File_To_PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="c5688-122">Receive port: File_To_PrivateResponder</span></span>  
  
  -   <span data-ttu-id="c5688-123">受信場所。File_To_PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="c5688-123">Receive location: File_To_PrivateResponder</span></span>  
  
  <span data-ttu-id="c5688-124">次の手順では、BTSTask コマンドを使用してバインド ファイルからバインドをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5688-124">The following procedure describes how to import the bindings from the binding files using the BTSTask command.</span></span> <span data-ttu-id="c5688-125">詳細については、BizTalk Server ヘルプの「ImportBindings コマンド」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5688-125">For more information, see the "ImportBindings Command" topic in BizTalk Server Help.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="c5688-126">手順</span><span class="sxs-lookup"><span data-stu-id="c5688-126">Procedure</span></span>  
  
#### <a name="to-set-up-btarn-by-using-file-drop-folders"></a><span data-ttu-id="c5688-127">ファイル ドロップ フォルダーを使用して BTARN を設定するには</span><span class="sxs-lookup"><span data-stu-id="c5688-127">To set up BTARN by using file drop folders</span></span>  
  
1.  <span data-ttu-id="c5688-128">BizTalk エクスプ ローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="c5688-128">Open BizTalk Explorer.</span></span>  
  
2.  <span data-ttu-id="c5688-129">2 つの LOB SQL 送信ポート、PrivateInitiator_To_LOB と PrivateResponder_To_LOB を停止します。</span><span class="sxs-lookup"><span data-stu-id="c5688-129">Stop the two LOB SQL send ports, PrivateInitiator_To_LOB and PrivateResponder_To_LOB.</span></span>  
  
3.  <span data-ttu-id="c5688-130">2 つの Lob SQL 受信ポート LOB_To_PrivateInitiator と LOB_To_PrivateResponder を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c5688-130">Disable the two Lob SQL Receive ports, LOB_To_PrivateInitiator and LOB_To_PrivateResponder.</span></span>  
  
4.  <span data-ttu-id="c5688-131">Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess の参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="c5688-131">Unenlist Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess.</span></span>  
  
5.  <span data-ttu-id="c5688-132">Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess の参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="c5688-132">Unenlist Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess.</span></span>  
  
6.  <span data-ttu-id="c5688-133">C:\Program files \microsoft BizTalk の BTARN フォルダーの下に \FileDrops フォルダーを作成する\<バージョン\>Accelerator for RosettaNet、し、\FileDrops の下の次のフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="c5688-133">Create a \FileDrops folder under the BTARN folder of C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet , and then create the following folder structure under \FileDrops:</span></span>  
  
    -   <span data-ttu-id="c5688-134">\PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="c5688-134">\PrivateInitiator</span></span>  
  
         <span data-ttu-id="c5688-135">\FromLOB</span><span class="sxs-lookup"><span data-stu-id="c5688-135">\FromLOB</span></span>  
  
         <span data-ttu-id="c5688-136">\ToLOB</span><span class="sxs-lookup"><span data-stu-id="c5688-136">\ToLOB</span></span>  
  
    -   <span data-ttu-id="c5688-137">\PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="c5688-137">\PrivateResponder</span></span>  
  
         <span data-ttu-id="c5688-138">\FromLOB</span><span class="sxs-lookup"><span data-stu-id="c5688-138">\FromLOB</span></span>  
  
         <span data-ttu-id="c5688-139">\ToLOB</span><span class="sxs-lookup"><span data-stu-id="c5688-139">\ToLOB</span></span>  
  
7.  <span data-ttu-id="c5688-140">(BTARN が c: ドライブにインストールされていることを想定)、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5688-140">Run the following command (assuming that BTARN is installed on the C: drive):</span></span>  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateInitiatorusingFileDrops.xml  
    ```  
  
8.  <span data-ttu-id="c5688-141">(BTARN が c: ドライブにインストールされていることを想定)、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5688-141">Run the following command (assuming that BTARN is installed on the C: drive):</span></span>  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateResponderusingFileDrops.xml  
    ```  
  
9. <span data-ttu-id="c5688-142">送信ポートを開始します。PrivateInitiator_To_File and PrivateResponder_To_File</span><span class="sxs-lookup"><span data-stu-id="c5688-142">Start the send ports: PrivateInitiator_To_File and PrivateResponder_To_File.</span></span>  
  
10. <span data-ttu-id="c5688-143">受信ポートを有効にします。LOB_To_PrivateInitiator and LOB_To_PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="c5688-143">Enable the receive ports: LOB_To_PrivateInitiator and LOB_To_PrivateResponder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5688-144">参照</span><span class="sxs-lookup"><span data-stu-id="c5688-144">See Also</span></span>  
 [<span data-ttu-id="c5688-145">メッセージ サンプル</span><span class="sxs-lookup"><span data-stu-id="c5688-145">Messaging Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)