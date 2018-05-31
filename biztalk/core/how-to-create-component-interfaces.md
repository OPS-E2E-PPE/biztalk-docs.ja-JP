---
title: コンポーネント インターフェイスを作成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 86ee68edba66b05d3c2541dd9c41cc074bd790b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249298"
---
# <a name="how-to-create-component-interfaces"></a>コンポーネント インターフェイスの作成方法
コンポーネント インターフェイスは、PeopleSoft アプリケーション デザイナーを使用して作成します  (アプリケーション デザイナの詳細については、PeopleSoft Enterprise のドキュメントを参照してください)。  
  
 コンポーネント ビューでは、レコードからプロパティを追加できます。 コンポーネント インターフェイスで、公開しないプロパティを削除できます。 プロパティをクリックし、新しい名前を入力できるようになるまで繰り返しクリックすることにより、プロパティの名前を変更できます。 プロパティの名前を変更した場合は、コンポーネント インターフェイスで、基になるコンポーネント名ではなく、新しい名前のみでそのプロパティを参照できます。  
  
 プロパティには、その横にさまざまなアイコンがある場合があります。 たとえば、EMPLID には、それが基になるレコードからのキー フィールドであることを示すアイコンがあります。 NAME には、それが基になるレコードからの代替キー フィールドであることを示すアイコンがあります  (全プロパティ アイコンの一覧については、PeopleBooks のドキュメントを参照してください)。  
  
### <a name="creating-a-new-component-interface"></a>新しいコンポーネント インターフェイスの作成  
  
1.  PeopleSoft アプリケーション デザイナを開きます。  
  
2.  **[ファイル]** メニューの **[新規作成]** をクリックします。  
  
     ![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")  
  
3.  **新規**ダイアログ ボックスで、**コンポーネント インターフェイス**、順にクリック**OK**です。  
  
     ![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")  
  
4.  **コンポーネント インターフェイスのソース コンポーネントを選択して**ウィンドウで、コンポーネント インターフェイスの基礎として使用し、をクリックするコンポーネントを選択**選択**です。  
  
     ![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")  
  
    > [!NOTE]
    >  コンポーネント インターフェイスが大きい場合は、コンポーネントのプロパティを手動で公開します。  
  
5.  **アプリケーション デザイナー**  ダイアログ ボックスで、次のオプションのいずれかを選択します。  
  
    -   をクリックして**いいえ**プロパティを表示することがなく、コンポーネント インターフェイスを作成して、コンポーネントのプロパティを手動で公開します。  
  
         a. 左側のペインから右側のペインに関連するフィールドをドラッグします。  
  
         b. 実行するさまざまな機能を選択するには、か、どのウィンドウがアクティブなに応じての右または左のペインを右クリックします。  
  
         全機能の一覧については、PeopleBooks のドキュメントを参照してください。  
  
    -   をクリックして**はい**コンポーネント インターフェイスを作成し、基になるコンポーネント インターフェイスのプロパティを表示します。  
  
         ![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")  
  
## <a name="see-also"></a>参照  
 [コンポーネント インターフェイスの標準メソッド](../core/standard-methods-in-component-interfaces.md)   
 [付録 c: コンポーネント インターフェイスの使用](../core/appendix-c-using-component-interfaces.md)   
 [付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)