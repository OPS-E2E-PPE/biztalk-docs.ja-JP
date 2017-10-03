---
title: "タスク 4: 構成コンストラクト メッセージ Shape1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3e66a9d-c549-42d0-849b-9e1744056429
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f781e03f83223f7d82628ee9c01728a0754b149f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="task-4-configure-the-construct-message-shape"></a>タスク 4: メッセージの構築図形を構成します。
メッセージの構築には、メッセージの割り当てと共に、ドキュメントの開始、編集、および終了の各コードに関する指示が格納されます。  
  
 メッセージの構築図形を構成するには、次の手順に従います。  
  
### <a name="to-configure-the-construct-message-shape"></a>メッセージの構築図形を構成するには  
  
1.  メッセージの構築図形を [ReceiveBeginDoc] と [SendBeginDoc] の間にドラッグします。  
  
    -   **構築メッセージ:** BeginDocSessionMsg  
  
    -   **[名前]:** ConstructBeginDocMessageWithSession  
  
    1.  新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。  
  
    2.  内側の MessageAssignment_1 図形をダブルクリックします。  
  
         BizTalk 式エディターが表示されます。  
  
    3.  コードを入力します。コード例は次のとおりです。  
  
        ```  
        BeginDocSessionMsg = BeginDocMsg;  
        BeginDocSessionMsg(JDE.ReserveSession) = true;  
        BeginDocSessionMsg(JDE.SessionID) = 0;  
        ```  
  
         これにより、セッションを開始するようにアダプタに指示できます。 SessionID は 0 として初期化されますが、応答が返さ ID はで割り当てられます、j. d. Edwards EnterpriseOne サーバー。  
  
     ![メッセージ式エディター](../core/media/message-expression-editor.gif "message_expression_editor")  
  
2.  メッセージの構築図形を [SendEditLine] の前にドラッグします。  
  
    -   **構築メッセージ:** EditLineSessionMsg  
  
    -   **[名前]:** ConstructEditLineMessageWithSession  
  
     ![編集行を送信](../core/media/constructoreditlinemessagewithsession.gif "constructoreditlinemessagewithsession")  
  
    1.  新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。  
  
    2.  内側の MessageAssignment_1 図形をダブルクリックします。  
  
         BizTalk 式エディターが表示されます。  
  
    3.  コードを入力します。コード例は次のとおりです。  
  
        ```  
        EditLineSessionMsg = EditLineMsg;  
        EditLineSessionMsg(JDE.ReserveSession) = true;  
        EditLineSessionMsg(JDE.SessionID) =  
        BeginDocResponseMsg(JDE.SessionID);  
        ```  
  
     ![編集行エディター](../core/media/editline-editor.gif "editline_editor")  
  
3.  SendEndDoc の前にメッセージの構築図形をドラッグします。  
  
    -   **構築メッセージ:** EndDocSessionMsg  
  
    -   **[名前]:** ConstructEndDocMessageWithSession  
  
    1.  新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。  
  
    2.  内側の MessageAssignment_1 図形をダブルクリックします。  
  
         BizTalk 式エディターが表示されます。  
  
    3.  コードを入力します。コード例は次のとおりです。  
  
        ```  
        EndDocSessionMsg = EndDocMsg;  
        EndDocSessionMsg(JDE.ReserveSession) = false;  
        EndDocSessionMsg(JDE.SessionID) =  
           BeginDocResponseMsg(JDE.SessionID);  
        ```  
  
## <a name="see-also"></a>参照  
 [タスク 1: ポートを作成します。](../core/task-1-create-the-ports1.md)   
 [タスク 2: メッセージを作成します。](../core/task-2-create-the-messages2.md)   
 [タスク 3: 送信、受信図形と構成](../core/task-3-configure-the-send-and-receive-shapes2.md)   
 [タスク 5: 変換図形を構成します。](../core/task-5-configure-the-transform-shape2.md)