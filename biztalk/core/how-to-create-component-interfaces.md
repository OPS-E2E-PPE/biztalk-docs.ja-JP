---
title: コンポーネント インターフェイスを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating component interfaces
- component interfaces, creating
ms.assetid: 9def053a-cbf6-4b34-b2e8-b2d03bffc5fe
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 778f9b59db2712fffb50d5e83e55155386ed81d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339445"
---
# <a name="how-to-create-component-interfaces"></a>コンポーネント インターフェイスを作成する方法
PeopleSoft アプリケーション デザイナを使用してコンポーネント インターフェイスを作成します。 (アプリケーション デザイナーの詳細については、PeopleSoft Enterprise のドキュメントを参照してください)。  
  
 コンポーネント ビュー内のレコードからプロパティを追加することができます。 コンポーネント インターフェイスで公開したくないプロパティを削除できます。 プロパティの名前を変更するには、プロパティをクリックして新しい名前を入力するまでもう一度クリックします。 プロパティの名前を変更する場合参照できますが、コンポーネント インターフェイスで新しい名前のみで、基になるコンポーネント名ではなく。  
  
 プロパティには、さまざまなアイコンに隣接する可能性があります。 たとえば、EMPLID には、基になるレコードからキー フィールドであることを示すアイコンがあります。 名前が、アイコンを基になるレコードからの代替キー フィールドであることを示します。 (プロパティのアイコンの一覧は、PeopleBooks のドキュメントを参照してください)。  
  
### <a name="creating-a-new-component-interface"></a>新しいコンポーネント インターフェイスを作成します。  
  
1.  PeopleSoft アプリケーション デザイナーを開きます。  
  
2.  **[ファイル]** メニューの **[新規作成]** をクリックします。  
  
     ![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")  
  
3.  **新規**ダイアログ ボックスで、**コンポーネント インターフェイス**、順にクリックします**OK**します。  
  
     ![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")  
  
4.  **のコンポーネント インターフェイスの変換元コンポーネントの選択**ウィンドウで、クリックして、コンポーネント インターフェイスの基礎として使用するコンポーネントを選択**選択**します。  
  
     ![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")  
  
    > [!NOTE]
    >  コンポーネント インターフェイスのサイズが大きい場合は、手動でコンポーネントのプロパティを公開します。  
  
5.  **アプリケーション デザイナー**  ダイアログ ボックスで、次のオプションのいずれかを選択します。  
  
    -   クリックして**いいえ**プロパティを表示せずに、コンポーネント インターフェイスを作成して、コンポーネントのプロパティを手動で公開します。  
  
         A. 左側のペインから右側のペインに関連するフィールドをドラッグします。  
  
         B. 実行するさまざまな機能を選択するには、かに応じてどのペインがアクティブの右側または左側のウィンドウを右クリックします。  
  
         関数の完全な一覧は、PeopleBooks のドキュメントを参照してください。  
  
    -   クリックして**はい**コンポーネント インターフェイスを作成し、基になるコンポーネント インターフェイスのプロパティを表示します。  
  
         ![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")  
  
## <a name="see-also"></a>参照  
 [コンポーネント インターフェイスの標準メソッド](../core/standard-methods-in-component-interfaces.md)   
 [付録 c:コンポーネント インターフェイスの使用](../core/appendix-c-using-component-interfaces.md)   
 [付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)