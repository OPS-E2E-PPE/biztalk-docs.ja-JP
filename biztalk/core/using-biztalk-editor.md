---
title: "BizTalk エディターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22021272-f028-4db3-ad8a-fb89a5340910
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdb293e6255042a46ecef16855d723c38543310c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-editor"></a>BizTalk エディターの使用

## <a name="overview"></a>概要
BizTalk エディターは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルの一部です。 BizTalk エディターの一部の機能は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルの既存のユーザー インターフェイス要素を利用しています。 たとえば、使用する、**ファイル**、**編集**と**ビュー**と同様のメニュー内で他の開発と[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。 この共通の機能に関する情報はから利用可能な**ヘルプ**メニュー。  
  
 BizTalk エディターは、新しいスキーマを BizTalk プロジェクトに追加した場合、BizTalk プロジェクトで既存のスキーマ (.xsd ファイル) を開いた場合、または [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウでスキーマのタブをクリックしてスキーマを再アクティブ化した場合にアクティブになります。  
  
> [!NOTE]
>  BizTalk エディターでは、UTF-16 文字エンコードを使用してスキーマ ファイルを保存します。  

## <a name="views"></a>ビュー  
 次の図は、BizTalk エディターの一部である Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルのさまざまなビューを示しています。  
  
 ![BizTalk プロジェクトのさまざまな部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")  
  
 BizTalk エディターは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルの次のビューと関連するダイアログ ボックスで構成されます。  
  
-   **スキーマ ツリー。** このビューは、メインの左側に[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。 スキーマで定義されるメッセージの構造を示すツリー構造を構築すると、このビューでスキーマがアクティブに作成されます。 スキーマ ツリー ビューでの BizTalk スキーマの表記方法の詳細については、次を参照してください。[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)です。  
  
-   **XSD を表示します。** このビューは、メインの右側に[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。 スキーマ ツリー ビューに構築されているスキーマを表す XSD (XML Schema Definition ) 言語構造を示します。 このビューは読み取り専用で、作成するスキーマの XSD 構文を理解するためのものです。 必要に応じて、ビューの分割機能を使用して、XSD ビューの表示を調整できます。  
  
-   **ソリューション エクスプ ローラー。** このビューは、の右側にある、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]シェルです。 BizTalk プロジェクトと BizTalk プロジェクトに含まれるさまざまな項目が表示されます。 ソリューション エクスプローラーを使用して、新しいスキーマおよび既存のスキーマをプロジェクトに追加したり、プロジェクトの一部であるスキーマを開いたりできます。 たとえば、新しいスキーマを作成するソリューション エクスプ ローラー ウィンドウで、BizTalk プロジェクトを右クリックし、をクリックして**追加**をクリックして**新しい項目の**、しを使用して、**新しい項目の追加**ダイアログボックス名前を指定し、新しいスキーマを作成します。  
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]  **プロパティ ウィンドウ。** : このビューを使用して、ほとんどのスキーマ プロパティおよびノード プロパティの確認および設定を行います。 スキーマ ツリー ビューのノードまたは [ソリューション エクスプローラー] ウィンドウのスキーマを選択すると、ノードやスキーマに対応するプロパティが標準の Visual Studio パラダイムで [プロパティ] ウィンドウに表示されます。 たとえば、プロパティは、カテゴリごとにグループ化されていたり、カテゴリ順またはアルファベット順に従って表示されたりします。 異なる種類のノード、または、スキーマが選択されているときに使用できるプロパティの異なるセットの詳細については、次を参照してください。、**スキーマ プロパティのリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
 これらのビュー以外にも、いくつかのダイアログ ボックスを使用できます。 通常、このようなダイアログ ボックスは、コレクションなど複雑なプロパティを編集する場合に使用します。  
  
 このセクションでは、BizTalk エディターで使用できるビュー、コマンド、およびショートカット キーに関する情報について説明します。  
  
## <a name="next-steps"></a>次の手順 
  
-   [スキーマ ツリー ビューを管理する方法](../core/how-to-manage-the-schema-tree-view.md)  
  
-   [XSD ビューを管理する方法](../core/how-to-manage-the-xsd-view.md)  
  
-   [[プロパティ] ウィンドウを管理する方法](../core/how-to-manage-the-properties-window.md)  
  
-   [その他の Visual Studio のウィンドウを管理する方法](../core/how-to-manage-other-visual-studio-windows.md)  
  
-   [BizTalk エディター コマンドの使用](../core/using-biztalk-editor-commands.md)  
  
-   [大きなスキーマの操作](../core/working-with-large-schemas.md)