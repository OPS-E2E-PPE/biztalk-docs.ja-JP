---
title: Visual Studio に PeopleSoft スキーマをインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 411f25f4-4431-44e4-84cf-5c515b3e32db
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6af82459f8b51f3dfa73a52593db18d25365c2a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013537"
---
# <a name="import-peoplesoft-schemas-into-biztalk-server-projects"></a>PeopleSoft スキーマを BizTalk Server プロジェクトにインポートします。
PeopleSoft Enterprise システムを作成したら、サーバーを参照し、スキーマを BizTalk Server プロジェクトにインポートできます。  
  
## <a name="browse-a-peoplesoft-server-system"></a>PeopleSoft サーバー システムを参照します。  
  
1.  BizTalk Server プロジェクトを右クリックし、次のいずれかのオプションを選択します。  
  
    -   既に、オブジェクトのスキーマを生成する場合は、選択**追加**をクリックして**スキーマの追加**し、オーケストレーションに追加する既存のスキーマを選択します。  
  
    -   オンの場合は、オブジェクトのスキーマを生成することはありません、**追加**、順にクリックして**生成した項目の追加**、アダプターを選択します。 これは、同じ名前で入力した、 **AdapterProperties** ] ダイアログ ボックス。 詳細については、BizTalk のメイン ヘルプで「[アダプターのプロパティ] ダイアログ ボックス」を参照してください。  
  
2.  [次へ] をクリックします。  
  
     PeopleSoft Enterprise システムがブラウザーに表示されます。  
  
     ![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")  
  
### <a name="component-interfaces"></a>コンポーネント インターフェイス  
 **コンポーネント インターフェイス**(CI) フォルダーでは、システムで使用可能なコンポーネントのすべてのインターフェイスを表示することができます。 コンポーネント インターフェイスでは、サポートされる一連のメソッドとプロパティが宣言されています。 動作またはプロパティはコンポーネント インターフェイスでは実装されていません。 Microsoft BizTalk Adapter for PeopleSoft Enterprise では、CreateEx、DeleteOnly、Find、Get、UpdateEx などの標準メソッドが公開されています。 これらのメソッドの説明は、次を参照してください。[付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)です。  
  
## <a name="generate-schemas"></a>スキーマを生成します。  
  
スキーマをインポートする項目を選択します。**メッセージ**、**クエリ**、または**コンポーネント インターフェイス**です。  選択した項目のスキーマが生成されて、BizTalk Server プロジェクトにインポートされます。  
  
> [!NOTE]
>  サーバー オブジェクトの定義を変更した場合は、スキーマを再生成して、含まれるデータを更新する必要があります。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)