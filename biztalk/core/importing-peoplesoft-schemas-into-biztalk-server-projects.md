---
title: PeopleSoft スキーマを Visual Studio にインポート |Microsoft Docs
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
ms.openlocfilehash: 89534c67d772f8b025289d61ab515f1585791d68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382481"
---
# <a name="import-peoplesoft-schemas-into-biztalk-server-projects"></a>PeopleSoft スキーマを BizTalk Server プロジェクトにインポートします。
PeopleSoft Enterprise システムを作成したら、サーバーを参照し、BizTalk Server プロジェクトにスキーマをインポートできます。  
  
## <a name="browse-a-peoplesoft-server-system"></a>PeopleSoft サーバー システムを参照します。  
  
1.  BizTalk Server プロジェクトを右クリックし、次のオプションのいずれかを選択します。  
  
    -   既に、オブジェクトのスキーマを生成する場合は、選択**追加**、 をクリックして**スキーマの追加、** し、オーケストレーションに追加する既存のスキーマを選択します。  
  
    -   オブジェクトのスキーマを生成しない場合は、選択**追加**、 をクリックし、**生成した項目の追加**、アダプターを選択します。 これは、同じ名前で入力、 **AdapterProperties**  ダイアログ ボックス。 詳細については、BizTalk のメイン ヘルプで「アダプターのプロパティ ダイアログ ボックス」を参照してください。  
  
2.  [次へ] をクリックします。  
  
     PeopleSoft Enterprise システムは、ブラウザーに表示されます。  
  
     ![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")  
  
### <a name="component-interfaces"></a>コンポーネント インターフェイス  
 **コンポーネント インターフェイス**(CI) フォルダー、システムですべての利用可能なコンポーネント インターフェイスを表示することができます。 コンポーネント インターフェイスでは、メソッドとサポートされるプロパティのセットを宣言します。 コンポーネント インターフェイスは、動作またはプロパティを実装していません。 Microsoft BizTalk Adapter for PeopleSoft Enterprise では、たとえば、CreateEx、DeleteOnly、Find、Get、および UpdateEx、標準的なメソッドを公開します。 これらのメソッドの説明は、次を参照してください[付録 a:。コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)します。  
  
## <a name="generate-schemas"></a>スキーマを生成します。  
  
スキーマをインポートする項目を選択します。**メッセージ**、**クエリ**、または**コンポーネント インターフェイス**します。  BizTalk Server では、選択した項目のスキーマが生成され、BizTalk Server プロジェクトにインポートします。  
  
> [!NOTE]
>  サーバー オブジェクトの定義を変更する場合が含まれているデータを更新するスキーマを再生成する必要があります。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)