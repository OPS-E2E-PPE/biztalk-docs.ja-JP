---
title: "FileTransport サンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a32c8cbf-0c17-4237-b2a3-9d21faa13496
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38c08be5cd58ed6c80af351715ff6257f533c6af
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="filetransport-sample"></a>FileTransport サンプル
FileTransport サンプルは、SQL ポートの代わりにファイル ポートを使用するように [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] を設定する方法を示します。 FileTransport サンプルは、HTTP の代わりにファイル転送プロトコル (FTP) を使用してメッセージを送受信します。  
  
> [!NOTE]
>  このドキュメントでは、内部テストまたは説明を目的として [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] をインストールすることを前提としており、 最小セキュリティ アカウントやセットアップについては説明しません。 このトピックの手順に従うには、ローカル管理権限を持つアカウントを使用する必要があります。  
  
> [!NOTE]
>  このサンプルはメッセージの添付ファイルをサポートしていません。  
  
## <a name="filetransport-binding-files"></a>FileTransport バインド ファイル  
 FileTransport サンプルには、2 つのバインド ファイルが含まれています。 各バインド ファイルを使用すると、BTARN のオーケストレーションで使用するファイル ポートを設定できます。 これらのバインド ファイルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet \SDK\FileTransport です。 次に示すように、オーケストレーション、送信ポート、受信ポート、および受信場所に関する設定を確認するには、各バインド ファイルをメモ帳などのエディターで開きます。  
  
-   PrivateInitiatorusingFileDrops.xml  
  
    -   オーケストレーション : Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess  
  
    -   送信ポート : PrivateInitiator_To_File  
  
    -   受信ポート : File_To_PrivateInitiator  
  
    -   受信場所 : File_To_PrivateInitiator  
  
-   PrivateResponderusingFileDrops.xml  
  
    -   オーケストレーション : Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess  
  
    -   送信ポート : PrivateResponder_To_File  
  
    -   受信ポート : File_To_PrivateResponder  
  
    -   受信場所 : File_To_PrivateResponder  
  
 次の手順では、BTSTask コマンドを使用してバインド ファイルからバインドをインポートする方法について説明します。 詳細については、BizTalk Server ヘルプの「ImportBindings コマンド」を参照してください。  
  
## <a name="procedure"></a>手順  
  
#### <a name="to-set-up-btarn-by-using-file-drop-folders"></a>ファイル格納フォルダを使用して BTARN を設定するには  
  
1.  BizTalk エクスプローラを開きます。  
  
2.  PrivateInitiator_To_LOB と PrivateResponder_To_LOB という、2 つの LOB SQL 送信ポートを停止します。  
  
3.  LOB_To_PrivateInitiator と LOB_To_PrivateResponder という、2 つの Lob SQL 受信ポートを無効にします。  
  
4.  Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess の登録を解除します。  
  
5.  Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess の登録を解除します。  
  
6.  C:\Program files \microsoft BizTalk の BTARN フォルダーの下に \FileDrops フォルダーを作成する\<バージョン\>Accelerator for RosettaNet、し、\FileDrops の下にある次のフォルダー構造を作成します。  
  
    -   \PrivateInitiator  
  
         \FromLOB  
  
         \ToLOB  
  
    -   \PrivateResponder  
  
         \FromLOB  
  
         \ToLOB  
  
7.  次のコマンドを実行します (BTARN が C: ドライブにインストールされていると仮定します)。  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateInitiatorusingFileDrops.xml  
    ```  
  
8.  次のコマンドを実行します (BTARN が C: ドライブにインストールされていると仮定します)。  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateResponderusingFileDrops.xml  
    ```  
  
9. 送信ポート PrivateInitiator_To_File と PrivateResponder_To_File を開始します。  
  
10. 受信ポート LOB_To_PrivateInitiator と LOB_To_PrivateResponder を有効にします。  
  
## <a name="see-also"></a>参照  
 [メッセージ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)