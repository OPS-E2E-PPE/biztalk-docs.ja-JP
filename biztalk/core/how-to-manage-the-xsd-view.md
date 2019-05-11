---
title: XSD ビューを管理する方法 |Microsoft Docs
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
ms.openlocfilehash: 6aa052fffcb50854b43cd8b1df169c026e4c0320
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384608"
---
# <a name="how-to-manage-the-xsd-view"></a>XSD ビューを管理する方法
に関しては、XSD ビューの管理タスクは、3 種類に分けることができます。 そのサイズを変更する、その背景色とフォントの変更、および更新特性を変更します。  
  
 更新特性の変更、後者に分類が最も役に立つ更新が望ましくない遅延を引き起こす可能性がありますの自動の大規模なスキーマを使用する場合。 このような場合、自動 (連続) 更新を無効にし、代わりに、必要に応じて手動で XSD ビューを更新できます。  
  
 このトピックでは、これらのタスクの詳細な手順を説明します。  
  
### <a name="to-make-the-xsd-view-taller-or-shorter"></a>XSD ビューのサイズを垂直方向に変更するには  
  
1. Microsoft の下端にマウス ポインターを移動[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]メイン編集ウィンドウが標準的なウィンドウの垂直方向サイズ変更アイコンにカーソルが変更されるまで、XSD ビューのサイドとスキーマ ツリー ビューが表示されます。  
  
2. クリックし、マウスの左ボタンを押したままおよび上または下のウィンドウの端をドラッグします。  
  
    メイン編集ウィンドウ全体を垂直方向にサイズ変更によって、XSD ビューのサイズを変更できますが垂直方向に。  
  
### <a name="to-make-the-xsd-view-wider-or-more-narrow"></a>XSD ビューの水平方向にサイズ変更するには  
  
1. ペインの区切り線にマウス ポインターを移動、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]メイン編集ウィンドウで、カーソルは、標準のウィンドウ アイコンのサイズを水平方向に変更されるまでに、スキーマ ツリー ビューから、XSD ビューを分割します。  
  
2. クリックして、マウスの左 (狭くする) ボタンと左 (広くする) か、右ペインの端をドラッグします。  
  
    XSD ビューがスキーマ ツリー ビューを基準に、メイン編集ウィンドウの量を変更することで、XSD ビューのサイズを変更してが水平方向にします。  
  
    メイン編集ウィンドウ全体を水平方向にサイズ変更によって、XSD ビューの幅を広げたり狭めたりを行うことができます。  
  
### <a name="to-change-the-background-color-andor-font-used-by-the-xsd-view"></a>背景色/XSD ビューで使用されるフォントを変更するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]で、 **[ツール]** メニューの **[オプション]** をクリックします。  
  
2. **オプション**ダイアログ ボックスで、BizTalk エディター フォルダーをクリックし、必要に応じて、展開、**スキーマの表示**プラス記号をクリックしてカテゴリ (+) アイコン。  
  
3. ドロップダウン リストのカラー ピッカーを使用して背景色/フォントを変更または**フォント**に関連付けられているダイアログ ボックス、 **XSD ビューの背景色**と**XSD ビューのフォント**プロパティは、それぞれします。  
  
    アクセス、**フォント**、省略記号を使用して、ダイアログ ボックス (**.**) ボタンの右端にある、 **XSD ビューのフォント**プロパティ値ボックス。  
  
### <a name="to-turn-automatic-refresh-of-the-xsd-view-on-and-off"></a>XSD ビューの自動更新を有効または無効にする  
  
-   BizTalk エディターでは、下、 **XSD** ] タブで [**自動更新をオフに**または**自動更新を有効**。  
  
     自動更新がオフの場合は、XSD ビューが空白です。  
  
    > [!IMPORTANT]
    >  既定で自動更新はオンです。 スキーマし、自動更新機能をオフにし、スキーマを必要に応じて手動で更新することがますます重要になりますが大きく、します。  
  
### <a name="to-manually-refresh-the-xsd-view"></a>XSD ビューを手動で更新するには  
  
-   **BizTalk**  メニューのをクリックして**XSD の更新**します。  
  
     XSD では、スキーマ ツリーに対して行った変更を反映して更新プログラムを表示します。  
  
    > [!NOTE]
    >  クリックして、XSD ビューを更新することができますも手動で**XSD の更新**かをクリックして、スキーマ ツリー内のすべてのノードに関連付けられているショートカット メニューで、**更新**以下のリンク、 **XSD** XSD ビュー タブで。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターを使用してください。](../core/using-biztalk-editor.md)