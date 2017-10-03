---
title: "BizTalk Server プロジェクトへの PeopleSoft スキーマのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
- component interfaces
- BizTalk Server, schemas [PeopleSoft]
- importing schemas into BizTalk Server
ms.assetid: 411f25f4-4431-44e4-84cf-5c515b3e32db
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4946b438adc0d1e4d360b35207ff69e85b4e2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-peoplesoft-schemas-into-biztalk-server-projects"></a>PeopleSoft スキーマを BizTalk Server プロジェクトにインポートする
PeopleSoft Enterprise システムを作成したら、サーバーを参照し、スキーマを BizTalk Server プロジェクトにインポートできます。  
  
## <a name="browsing-a-peoplesoft-server-system"></a>PeopleSoft サーバー システムの参照  
 PeopleSoft サーバーを参照するには、アダプター ウィザードを使用します。  
  
#### <a name="to-browse-a-peoplesoft-server-system"></a>PeopleSoft サーバー システムを参照するには  
  
1.  BizTalk Server プロジェクトを右クリックし、次のいずれかのオプションを選択します。  
  
    -   既に、オブジェクトのスキーマを生成する場合は、選択**追加**をクリックして**スキーマの追加**し、オーケストレーションに追加する既存のスキーマを選択します。  
  
    -   オンの場合は、オブジェクトのスキーマを生成することはありません、**追加**、順にクリックして**生成した項目の追加**、アダプターを選択します。 これは、同じ名前で入力した、 **AdapterProperties**  ダイアログ ボックス。 詳細については、BizTalk のメイン ヘルプで「[アダプターのプロパティ] ダイアログ ボックス」を参照してください。  
  
2.  [次へ] をクリックします。  
  
     PeopleSoft Enterprise システムがブラウザーに表示されます。  
  
     ![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")  
  
### <a name="component-interfaces"></a>コンポーネント インターフェイス  
 **コンポーネント インターフェイス**(CI) フォルダーでは、システムで使用可能なコンポーネントのすべてのインターフェイスを表示することができます。 コンポーネント インターフェイスでは、サポートされる一連のメソッドとプロパティが宣言されています。 動作またはプロパティはコンポーネント インターフェイスでは実装されていません。 Microsoft BizTalk Adapter for PeopleSoft Enterprise では、CreateEx、DeleteOnly、Find、Get、UpdateEx などの標準メソッドが公開されています。 これらのメソッドの説明は、次を参照してください。[付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)です。  
  
## <a name="generating-schemas"></a>スキーマを生成します。  
 スキーマを生成するには、次の手順を実行します。  
  
#### <a name="to-generate-the-schemas"></a>スキーマを生成するには  
  
-   スキーマをインポートする項目を選択します。**メッセージ**、**クエリ**、または**コンポーネント インターフェイス**です。  
  
     選択した項目のスキーマが生成されて、BizTalk Server プロジェクトにインポートされます。  
  
    > [!NOTE]
    >  サーバー オブジェクトの定義を変更した場合は、スキーマを再生成して、含まれるデータを更新する必要があります。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)