---
title: チュートリアル:TIBCO EMS メッセージ コンテキスト プロパティの使用 |Microsoft Docs
description: BizTalk Server のオーケストレーションで TIBCO Enterprise Message Service メッセージ記述子フィールドを使用するステップ バイ ステップ ガイド
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef7ce23a38c528b3dc7e3d0a3d98c39412e9c175
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393849"
---
# <a name="tutorial-use-tibco-ems-message-descriptors"></a>チュートリアル:TIBCO EMS メッセージ記述子を使用します。

## <a name="overview"></a>概要
このチュートリアルでは、BizTalk Server コンテキスト プロパティを使用して、オーケストレーションで TIBCO Enterprise Message Service (EMS) のメッセージ記述子フィールドを設定する方法を示します。 このチュートリアルでは、受信ポートからメッセージを受信し、TIBCO Enterprise Message Service for Microsoft BizTalk アダプターにバインドされた送信ポートにメッセージを送信するオーケストレーションがあることを前提とします。  
  
 次の手順では、TibcoEMS.Priority コンテキスト プロパティの値を変更することで、TIBCO EMS メッセージの優先度を変更する方法を示します。 BizTalk Server で、メッセージは変更できません。 そのため、プロパティ値を変更するには、作成および、新しいメッセージを変更する必要があります。 作成し、受信および送信図形の間でメッセージの割り当て図形を挿入することで、新しいメッセージを変更します。 最初に、ただし、する必要があります、スキーマ DLL を参照、TIBCO EMS プロパティにアクセスします。  
  
## <a name="reference-the-schema-dll"></a>スキーマ DLL を参照します。  
  
1.  Visual Studio で、BizTalk Server プロジェクトを開くし、開く**ソリューション エクスプ ローラー**します。  
  
2.  右クリック**参照**、選び**参照の追加**します。  
  
     **[参照の追加]** ダイアログ ボックスが表示されます。  
  
3.  をクリックして、**参照**タブ。  
  
     **コンポーネントの選択** ダイアログ ボックスが表示されます。  
  
4.  検索 **\<TIBCO EMS_Adapter_installation_directory\>\bin**、し、 **Microsoft.Adapters.TibcoEMSProperties.dll**します。  
  
5.  **[開く]** をクリックします。  
  
     DLL が表示されます、**選択されたコンポーネント**で、**参照の追加** ダイアログ ボックス。  
  
6.  クリックして**OK**し、オーケストレーション デザイナにアクセスするオーケストレーションをダブルクリックします。  
  
7.  **ビュー**メニューで、**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
8.  オーケストレーション ビューで右クリックして**メッセージ**選択と**新しいメッセージ**します。  
  
9. 新しいメッセージのプロパティを編集し、割り当てる、**メッセージの種類**します。  
  
     Message_1 を Message_2 に割り当てます。 そのため、メッセージの両方に同じメッセージの種類を割り当てる必要があります。  
  
10. **[表示]** メニューの **[ツールボックス]** をクリックします。  
  
11. ドラッグ、**メッセージの割り当て**図形に新しいメッセージを作成するオーケストレーションです。  
  
12. 外側の ConstructMessage_1 図形を編集しで、新しいメッセージ Message_2 を選択、**構築メッセージ**プロパティ。  
  
13. 内側の MessageAssignment_1 図形をダブルクリックします。  
  
     BizTalk 式エディターが表示されます。  
  
14. BizTalk 式エディターでは、コードを入力します。  
  
15. まず、既存のメッセージをコピーし、メッセージ コンテキスト プロパティに値を割り当てます。  
  
     構文は`Message(property) = value;`します。 以下に例を示します。  
  
    ```  
    Message_2 = Message_1;  
    Message_2( TibcoEMS.Priority) = 6;  
    ```  
  
     カスタム メッセージで使用できるサポートされているプロパティの一覧については、TIBCO EMS を参照してください。  
  
16. クリックして**OK** BizTalk 式エディターを終了し、コードを保存します。  
  
17. 送信図形をクリックし、割り当てる、**メッセージ**する**Message_2**します。  
  
18. メッセージ フローの残りの部分で図形を適切なメッセージで動作することを確認します。  
  
19. ソリューション エクスプ ローラーでプロジェクトを右クリックして**ビルド**します。  
  
20. プロジェクトを右クリックして**デプロイ**します。  
  
21. 選択**バインド**、**参加**、および**開始**オーケストレーションをテストする BizTalk エクスプ ローラーでします。  
  
## <a name="see-also"></a>参照  
[TIBCO EMS メッセージ コンテキスト プロパティ](../core/message-context-properties-in-biztalk-server.md)