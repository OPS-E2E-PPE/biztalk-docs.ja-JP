---
title: XSD ビューを管理する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3245ebf0-6128-47b4-8e88-ea06ececbc15
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 945f3fc4d8eac3b09279ea774209a9f43a0f6bd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254434"
---
# <a name="how-to-manage-the-xsd-view"></a>XSD ビューの管理方法
XSD ビューの管理タスクは、3 つのカテゴリに分類できます。 そのサイズを変更する、その背景色とフォントの変更、および更新特性の変更。  
  
 特に更新特性の変更はスキーマの規模が大きい場合に有用です。スキーマの規模が大きいと、自動更新に時間かかる場合があるためです。 このような場合は、自動 (連続) 更新を無効にし、必要に応じて手動で XSD ビューを更新できます。  
  
 このトピックでは、これらの作業手順について説明します。  
  
### <a name="to-make-the-xsd-view-taller-or-shorter"></a>XSD ビューのサイズを垂直方向に変更するには  
  
1.  XSD ビューとスキーマ ツリー ビューが並んで表示されている Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウで、マウス ポインターをウィンドウの下枠に移動すると、カーソルのアイコンが、ウィンドウのサイズを垂直方向に変更する標準的なアイコンに変わります。  
  
2.  マウスの左ボタンをクリックし、ボタンを押しながらウィンドウの下枠を上または下にドラッグします。  
  
     メイン編集ウィンドウ全体を垂直方向にサイズ変更することにより、XSD ビューを垂直方向にサイズ変更できます。  
  
### <a name="to-make-the-xsd-view-wider-or-more-narrow"></a>XSD ビューのサイズを水平方向に変更するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウで、マウス ポインターをペイン分割バー (XSD ビューとスキーマ ツリー ビューを区切る線) に移動すると、カーソルのアイコンが、ウィンドウのサイズを水平方向に変更する標準的なアイコンに変わります。  
  
2.  マウスの左ボタンをクリックし、ボタンを押しながらペインの端を左 (広くする) または右 (狭くする) にドラッグします。  
  
     メイン編集ウィンドウ内でスキーマ ツリー ビューと XSD ビューが占める割合を水平方向に変更することにより、XSD ビューを水平方向にサイズ変更できます。  
  
     また、メイン編集ウィンドウ全体を水平方向にサイズ変更することによって、XSD ビューの幅を変更することもできます。  
  
### <a name="to-change-the-background-color-andor-font-used-by-the-xsd-view"></a>XSD ビューで使用される背景色/フォントを変更するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]で、 **[ツール]** メニューの **[オプション]** をクリックします。  
  
2.  **オプション**ダイアログ ボックスでは、BizTalk エディター フォルダー をクリックし、必要に応じて、展開、**スキーマの表示**プラス記号をクリックしてカテゴリ (+) アイコン。  
  
3.  ドロップダウンのカラー ピッカーを使用して、背景色またはフォントを変更または**フォント** ダイアログ ボックスに関連付けられている、 **XSD ビューの背景色**と**XSD ビューのフォント**プロパティは、それぞれします。  
  
     アクセス、**フォント**、省略記号ボタンを使用して、ダイアログ ボックス (**.**) ボタンの右端にある、 **XSD ビューのフォント**プロパティ値ボックスです。  
  
### <a name="to-turn-automatic-refresh-of-the-xsd-view-on-and-off"></a>XSD ビューの自動更新をオン/オフにするには  
  
-   BizTalk エディターでは、下、 **XSD** ] タブで、をクリックして**自動更新をオフにする**または **[自動更新を有効**です。  
  
     自動更新がオフの場合、XSD ビューには何も表示されません。  
  
    > [!IMPORTANT]
    >  既定では、自動更新はオンになっています。 スキーマは、その規模が大きくなるにつれて、更新に時間がかかるようになります。更新時間が長すぎる場合は、自動更新機能をオフにし、必要に応じてスキーマを手動で更新する必要があります。  
  
### <a name="to-manually-refresh-the-xsd-view"></a>XSD ビューを手動で更新するには  
  
-   **BizTalk**  メニューのをクリックして**XSD の更新**です。  
  
     XSD ビューが更新され、スキーマ ツリーに対して行ったすべての変更が反映されます。  
  
    > [!NOTE]
    >  クリックして、XSD ビューを更新することができますも手動で**XSD の更新**スキーマ ツリーで、またはをクリックして、すべてのノードに関連付けられているショートカット メニューを開き、**更新**以下のリンク、 **XSD** XSD ビュー タブでします。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターの使用](../core/using-biztalk-editor.md)