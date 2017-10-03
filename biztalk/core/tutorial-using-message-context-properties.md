---
title: "チュートリアル: メッセージ コンテキスト プロパティの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, changing priority
- message context properties, tutorial
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f122215baa5660294e159e4f1d6967a2df5ba9b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-message-context-properties"></a>チュートリアル: メッセージ コンテキスト プロパティの使用
このチュートリアルでは、BizTalk Server コンテキスト プロパティを使用して、オーケストレーションで TIBCO Enterprise Message Service (EMS) のメッセージ記述子フィールドを設定する方法について説明します。 このチュートリアルでは、受信ポートからメッセージを受信し、Microsoft BizTalk Adapter for TIBCO Enterprise Message Service にバインドされた送信ポートにそのメッセージを送信するオーケストレーションがあることを前提としています。  
  
 次の手順では、TibcoEMS.Priority コンテキスト プロパティの値を変更することで、TIBCO EMS メッセージの優先度を変更する方法について説明します。 BizTalk Server では、メッセージを変更できません。 そのため、プロパティ値を変更するには、作成および、新しいメッセージを変更する必要があります。 作成して、受信および送信図形の間でメッセージの割り当て図形を挿入することで、新しいメッセージを変更します。 ただし、TIBCO EMS プロパティにアクセスできるようにするために、最初にスキーマ DLL を参照する必要があります。  
  
### <a name="to-reference-the-schema-dll"></a>スキーマ DLL を参照するには  
  
1.  開いている**ソリューション エクスプ ローラー** Visual Studio でします。  
  
2.  右クリック**参照**を選択して**参照の追加**です。  
  
     **[参照の追加]** ダイアログ ボックスが表示されます。  
  
3.  クリックして、**参照**タブです。  
  
     **コンポーネントの選択** ダイアログ ボックスが表示されます。  
  
4.  検索 **\<TIBCO EMS_Adapter_installation_directory > \bin**、し、 **Microsoft.Adapters.TibcoEMSProperties.dll**です。  
  
5.  **[開く]**をクリックします。  
  
     DLL が表示されます、**選択されたコンポーネント**で、**参照の追加** ダイアログ ボックス。  
  
6.  をクリックして**OK**し、オーケストレーションをダブルクリックして、オーケストレーション デザイナにアクセスするとします。  
  
7.  **ビュー**  メニューのをポイント**その他のウィンドウ**、順にクリック**オーケストレーション**です。  
  
8.  オーケストレーション ビューで右クリック**メッセージ**選択**新しいメッセージ**です。  
  
9. 新しいメッセージ プロパティを編集し、割り当てます、**メッセージの種類**です。  
  
     Message_1 を Message_2 に割り当てます。 したがって、両方のメッセージに同じメッセージの種類を割り当てる必要があります。  
  
10. **[表示]** メニューの **[ツールボックス]**をクリックします。  
  
11. ドラッグ、**メッセージの割り当て**図形に新しいメッセージを作成するオーケストレーションです。  
  
12. 外側の ConstructMessage_1 図形を編集しで、新しいメッセージ Message_2 を選択、**構築メッセージ**プロパティです。  
  
13. 内側の MessageAssignment_1 図形をダブルクリックします。  
  
     BizTalk 式エディターが表示されます。  
  
14. BizTalk 式エディターでは、コードを入力します。  
  
15. まず既存のメッセージをコピーし、メッセージのコンテキスト プロパティに値を割り当てます。  
  
     構文は `Message(property) = value;` です。 例:  
  
    ```  
    Message_2 = Message_1;  
    Message_2( TibcoEMS.Priority) = 6;  
    ```  
  
     カスタム メッセージで使用できる、サポートされているプロパティの一覧については、TIBCO EMS を参照してください。  
  
16. をクリックして**OK**して BizTalk 式エディタを終了し、コードを保存します。  
  
17. 送信図形をクリックし、割り当てる、**メッセージ**する**Message_2**です。  
  
18. メッセージ フローの残りの図形が該当するメッセージで動作することを確認します。  
  
19. ソリューション エクスプ ローラーでプロジェクトを右クリックし **ビルド**です。  
  
20. プロジェクトを右クリックし **展開**です。  
  
21. 選択**バインド**、 **Enlist**、および**開始**BizTalk エクスプ ローラーで、オーケストレーションをテストします。  
  
## <a name="see-also"></a>参照  
 [メッセージ コンテキスト プロパティ](../core/message-context-properties2.md)