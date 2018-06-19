---
title: ローカル サーバー上のアセンブリと型を表示する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 37c0f49559de7c4b1a13982578478cf249520479
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257322"
---
# <a name="how-to-view-assemblies-and-types-on-the-local-server"></a>ローカル サーバーにあるアセンブリと種類を表示する方法
BizTalk アセンブリ ビューアーを使用すると、ローカル サーバーにインストールされているすべての BizTalk アセンブリと種類を表示できます。  
  
### <a name="to-view-all-biztalk-server-assemblies-installed-in-the-gac"></a>GAC にインストールされているすべての BizTalk Server アセンブリを表示するには  
  
-   BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。  
  
     コンピューターのグローバル アセンブリ キャッシュ (GAC) にインストールされているすべての BizTalk アセンブリが表示されます。  
  
     ![](../core/media/ebiz-deply-asblyvieweropenpage.gif "ebiz_deply_asblyvieweropenpage")  
アセンブリ ビューアーの開始ページ  
  
### <a name="to-view-types-attributes-and-references-for-a-biztalk-assembly"></a>BizTalk アセンブリの種類、属性、および参照を表示するには  
  
1.  BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。  
  
2.  対象のアセンブリをダブルクリックします。  
  
     右ペインに、BizTalk アセンブリの種類が表示されます。 左ペインに、属性と種類が表示されます。  
  
     クリックして、アセンブリのインストール場所に移動することもできます、**コードベース**左上の作業ウィンドウの領域にリンクします。 (Windows エクスプローラーがフォルダー ビューになっているときは、作業ウィンドウがフォルダー リストで置き換えられるため、このリンクは表示されません)。  
  
### <a name="to-view-the-contents-of-a-type-in-a-biztalk-assembly"></a>BizTalk アセンブリの種類の内容を表示するには  
  
1.  BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。  
  
2.  対象のアセンブリをダブルクリックします。  
  
3.  右ペインで、対象の種類をダブルクリックします。  
  
     **コンテンツの種類ビューアー**ウィンドウが開き、XML 定義が表示されます。  
  
### <a name="to-add-a-biztalk-assembly-in-the-gac"></a>BizTalk アセンブリを GAC に追加するには  
  
1.  BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。  
  
2.  Windows エクスプローラーで、GAC に追加するアセンブリに移動します。  
  
3.  アセンブリをドラッグして、BizTalk アセンブリ ビューアーにドロップします。  
  
     BizTalk アセンブリ ビューアーは、BizTalk Server アセンブリのみを受け付けます。 BizTalk 以外のアセンブリをビューアーにドロップしても無視されます。  
  
### <a name="to-remove-a-biztalk-assembly-from-the-gac"></a>GAC から BizTalk アセンブリを削除するには  
  
1.  BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。  
  
2.  クリックして、GAC から削除するアセンブリを右クリックして**削除**です。  
  
### <a name="to-search-for-a-type-in-all-biztalk-assemblies"></a>すべての BizTalk アセンブリの種類を検索するには  
  
1.  BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。  
  
2.  メニュー バーからをクリックして、 **Biztalk Server 検索**アイコン。  
  
3.  [検索] ウィンドウ内の型を指定、**種類の検索**ドロップダウン リスト。  
  
4.  **BizTalk Server アセンブリ ファイルの場所**ドロップダウン リストで、検索対象のアセンブリを選択します。  
  
5.  指定した種類から参照されている種類だけが表示されるように検索を絞り込むには、次の手順を実行します。  
  
    1.  クリックして、**高度な検索条件**リンクします。  
  
    2.  **によって参照されている**ドロップダウン リストで、種類を選択します。  
  
    3.  **[検索]** をクリックします。  
  
         指定した種類が検索結果に表示されます。  
  
         ![](../core/media/ebiz-depl-asblyviewtypes.gif "ebiz_depl_asblyviewtypes")  
BizTalk アセンブリの種類  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリ ビューアーを使用してアセンブリを表示します。](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)