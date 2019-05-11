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
# <a name="filetransport-sample"></a>FileTransport サンプル
FileTransport サンプルは Microsoft® を構成する方法を示します[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SQL ポートではなくファイルのポートを使用します。 FileTransport サンプルでは、ファイル転送プロトコル (FTP) を使用して、HTTP ではなく、メッセージの送受信を行います。  
  
> [!NOTE]
>  このドキュメントは、インストールすることを想定しています[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]内部のテストまたはデモ目的のみ。 最小の任意のアカウントを規定したりを設定しません。 このトピックで、手順全体にわたって、ローカルの管理アクセス許可のあるアカウントを使用する必要があります。  
> 
> [!NOTE]
>  このサンプルは、メッセージの添付ファイルをサポートしていません。  
  
## <a name="filetransport-binding-files"></a>FileTransport バインド ファイル  
 FileTransport サンプルには、2 つのバインド ファイルが含まれています。 BTARN のオーケストレーションで使用するためにファイル ポートを設定するには、これらのバインド ファイルの各を使用できます。 これらのバインド ファイルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet \SDK\FileTransport します。 次に示すように、オーケストレーションの設定を表示、送信ポート、受信ポート、および受信場所をメモ帳などのエディターで各バインド ファイルを開きます。  
  
- PrivateInitiatorusingFileDrops.xml  
  
  -   オーケストレーション:Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess  
  
  -   送信ポート。PrivateInitiator_To_File  
  
  -   受信ポート。File_To_PrivateInitiator  
  
  -   受信場所。File_To_PrivateInitiator  
  
- PrivateResponderusingFileDrops.xml  
  
  -   オーケストレーション:Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess  
  
  -   送信ポート。PrivateResponder_To_File  
  
  -   受信ポート。File_To_PrivateResponder  
  
  -   受信場所。File_To_PrivateResponder  
  
  次の手順では、BTSTask コマンドを使用してバインド ファイルからバインドをインポートする方法について説明します。 詳細については、BizTalk Server ヘルプの「ImportBindings コマンド」のトピックを参照してください。  
  
## <a name="procedure"></a>手順  
  
#### <a name="to-set-up-btarn-by-using-file-drop-folders"></a>ファイル ドロップ フォルダーを使用して BTARN を設定するには  
  
1.  BizTalk エクスプ ローラーを開きます。  
  
2.  2 つの LOB SQL 送信ポート、PrivateInitiator_To_LOB と PrivateResponder_To_LOB を停止します。  
  
3.  2 つの Lob SQL 受信ポート LOB_To_PrivateInitiator と LOB_To_PrivateResponder を無効にします。  
  
4.  Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess の参加を解除します。  
  
5.  Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess の参加を解除します。  
  
6.  C:\Program files \microsoft BizTalk の BTARN フォルダーの下に \FileDrops フォルダーを作成する\<バージョン\>Accelerator for RosettaNet、し、\FileDrops の下の次のフォルダー構造を作成します。  
  
    -   \PrivateInitiator  
  
         \FromLOB  
  
         \ToLOB  
  
    -   \PrivateResponder  
  
         \FromLOB  
  
         \ToLOB  
  
7.  (BTARN が c: ドライブにインストールされていることを想定)、次のコマンドを実行します。  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateInitiatorusingFileDrops.xml  
    ```  
  
8.  (BTARN が c: ドライブにインストールされていることを想定)、次のコマンドを実行します。  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateResponderusingFileDrops.xml  
    ```  
  
9. 送信ポートを開始します。PrivateInitiator_To_File and PrivateResponder_To_File  
  
10. 受信ポートを有効にします。LOB_To_PrivateInitiator and LOB_To_PrivateResponder  
  
## <a name="see-also"></a>参照  
 [メッセージ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)