---
title: ローカル サーバーにアセンブリおよび型を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ddf6f60-9fef-4997-8b42-24eefd7ab0d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d119fa6672ca5b01470336b4f8749c96459112e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333073"
---
# <a name="how-to-view-assemblies-and-types-on-the-local-server"></a>ローカル サーバーにあるアセンブリと種類を表示する方法
BizTalk アセンブリ ビューアーを使用して、すべての BizTalk アセンブリと、ローカル サーバーにインストールされている型を確認することができます。  
  
### <a name="to-view-all-biztalk-server-assemblies-installed-in-the-gac"></a>GAC にインストールされているすべての BizTalk Server アセンブリを表示するには  
  
-   BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。  
  
     コンピューターのグローバル アセンブリ キャッシュ (GAC) にインストールされているすべての BizTalk アセンブリが表示されます。  
  
     ![](../core/media/ebiz-deply-asblyvieweropenpage.gif "ebiz_deply_asblyvieweropenpage")  
アセンブリ ビューアーの開始ページ  
  
### <a name="to-view-types-attributes-and-references-for-a-biztalk-assembly"></a>BizTalk アセンブリの型、属性、および参照を表示するには  
  
1.  BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。  
  
2.  適切なアセンブリをダブルクリックします。  
  
     BizTalk アセンブリの種類は、右側のウィンドウに表示されます。 属性と型は、左側のウィンドウに表示されます。  
  
     クリックして、アセンブリのインストール場所に移動することもできます、**コードベース** 作業ウィンドウの左上にリンクします。 (はフォルダーのビューでは Windows エクスプ ローラーでフォルダーの一覧で、作業ウィンドウが置き換えられるため、このリンクを表示にできません。)  
  
### <a name="to-view-the-contents-of-a-type-in-a-biztalk-assembly"></a>BizTalk アセンブリの型の内容を表示するには  
  
1.  BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。  
  
2.  適切なアセンブリをダブルクリックします。  
  
3.  右側のウィンドウで、適切な型をダブルクリックします。  
  
     **コンテンツの種類ビューアー**ウィンドウが開き、XML 定義が表示されます。  
  
### <a name="to-add-a-biztalk-assembly-in-the-gac"></a>BizTalk アセンブリを GAC に追加するには  
  
1.  BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。  
  
2.  Windows エクスプ ローラーを使用すると、GAC に追加するアセンブリに移動します。  
  
3.  アセンブリをドラッグし、BizTalk アセンブリ ビューアーにドロップします。  
  
     BizTalk アセンブリ ビューアーは、BizTalk Server アセンブリのみを受け入れます。 非 BizTalk アセンブリ ビューアーを削除する場合は無視されます。  
  
### <a name="to-remove-a-biztalk-assembly-from-the-gac"></a>BizTalk アセンブリを GAC から削除するには  
  
1.  BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。  
  
2.  クリックして、GAC から削除するアセンブリを右クリックして**削除**します。  
  
### <a name="to-search-for-a-type-in-all-biztalk-assemblies"></a>すべての BizTalk アセンブリ内の型を検索するには  
  
1.  BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。  
  
2.  メニュー バーからをクリックして、 **Biztalk Server 検索**アイコン。  
  
3.  [検索] ウィンドウで種類を指定、**種類の検索**ドロップダウン リスト。  
  
4.  **BizTalk Server アセンブリ立ち寄る**ドロップダウン リストで検索するアセンブリを選択します。  
  
5.  指定した型によって参照されている型のみを含めるために検索を絞り込むには、次の操作を行います。  
  
    1.  をクリックして、**検索条件の高度な**リンク。  
  
    2.  **によって参照される**ドロップダウン リストで、種類を選択します。  
  
    3.  **[検索]** をクリックします。  
  
         指定した型は、検索結果に表示されます。  
  
         ![](../core/media/ebiz-depl-asblyviewtypes.gif "ebiz_depl_asblyviewtypes")  
BizTalk アセンブリの種類  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリ ビューアーを使用したアセンブリの表示](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)