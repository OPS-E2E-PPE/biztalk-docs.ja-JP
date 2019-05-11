---
title: タスク 4:構成構造メッセージ図形 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e66a9d-c549-42d0-849b-9e1744056429
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ef7469d0c89305a8b13eca9306359c532d5689
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399213"
---
# <a name="task-4-configure-the-construct-message-shape"></a>タスク 4:メッセージの構築図形を構成します。
メッセージの構築では、開始、編集、およびドキュメントの終了コードの手順でメッセージの割り当てを保持します。  
  
 メッセージの構築図形を構成するのにには、次の手順を使用します。  
  
### <a name="to-configure-the-construct-message-shape"></a>メッセージの構築図形を構成するには  
  
1. メッセージの構築図形 receivebegindoc] と [をドラッグします。  
  
   -   **構築メッセージ:** BeginDocSessionMsg  
  
   -   **名:** ConstructBeginDocMessageWithSession  
  
   1. 新しいメッセージを作成するオーケストレーションにメッセージの割り当て図形をドラッグします。  
  
   2. 内側の MessageAssignment_1 図形をダブルクリックします。  
  
       BizTalk 式エディターが表示されます。  
  
   3. たとえば、コードに入力します。  
  
      ```  
      BeginDocSessionMsg = BeginDocMsg;  
      BeginDocSessionMsg(JDE.ReserveSession) = true;  
      BeginDocSessionMsg(JDE.SessionID) = 0;  
      ```  
  
       これにより、セッションを開始するアダプター。 SessionID は 0 として初期化されますが、ID を j. d. によって割り当てられますが、応答が返される Edwards EnterpriseOne サーバー。  
  
      ![メッセージ式エディター](../core/media/message-expression-editor.gif "message_expression_editor")  
  
2. SendEditLine する前にメッセージの構築をドラッグします。  
  
   - **構築メッセージ:** EditLineSessionMsg  
  
   - **名:** ConstructEditLineMessageWithSession  
  
     ![編集行を送信](../core/media/constructoreditlinemessagewithsession.gif "constructoreditlinemessagewithsession")  
  
   1. 新しいメッセージを作成するオーケストレーションにメッセージの割り当て図形をドラッグします。  
  
   2. 内側の MessageAssignment_1 図形をダブルクリックします。  
  
       BizTalk 式エディターが表示されます。  
  
   3. たとえば、コードに入力します。  
  
      ```  
      EditLineSessionMsg = EditLineMsg;  
      EditLineSessionMsg(JDE.ReserveSession) = true;  
      EditLineSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
      ```  
  
      ![編集行エディター](../core/media/editline-editor.gif "editline_editor")  
  
3. SendEndDoc の前にメッセージの構築図形をドラッグします。  
  
   -   **構築メッセージ:** EndDocSessionMsg  
  
   -   **名:** ConstructEndDocMessageWithSession  
  
   1.  新しいメッセージを作成するオーケストレーションにメッセージの割り当て図形をドラッグします。  
  
   2.  内側の MessageAssignment_1 図形をダブルクリックします。  
  
        BizTalk 式エディターが表示されます。  
  
   3.  たとえば、コードに入力します。  
  
       ```  
       EndDocSessionMsg = EndDocMsg;  
       EndDocSessionMsg(JDE.ReserveSession) = false;  
       EndDocSessionMsg(JDE.SessionID) =  
          BeginDocResponseMsg(JDE.SessionID);  
       ```  
  
## <a name="see-also"></a>参照  
 [タスク 1:ポートを作成します。](../core/task-1-create-the-ports1.md)   
 [タスク 2:メッセージを作成します。](../core/task-2-create-the-messages2.md)   
 [タスク 3:受信図形と送信の構成](../core/task-3-configure-the-send-and-receive-shapes2.md)   
 [タスク 5:変換図形を構成します。](../core/task-5-configure-the-transform-shape2.md)