---
title: ビューを管理する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4a865d7-b319-4264-a085-15f2155bdb2d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 553e471826cf4744638e7498fd2bb7d52b2e326a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254642"
---
# <a name="how-to-manage-views"></a>ビューを管理する方法
BizTalk マップを開発するには、処理を行って元または送信先スキーマ ツリー ビューのサイズまたはグリッド ビューのサイズを変更することがあります。 また、前に閉じた同じビューでマップを開きたい場合もあります。 このトピックでは、これらの作業手順について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-make-the-schema-tree-views-or-the-grid-view-taller-or-shorter"></a>スキーマ ツリー ビューまたはグリッド ビューを垂直方向にサイズ変更するには  
  
1.  メイン編集ウィンドウ (グリッド ビューと、その両側にスキーマ ツリーが表示されている) でマウス ポインターをウィンドウの下枠に移動すると、カーソルのアイコンが、ウィンドウのサイズを垂直方向に変更するための標準的なアイコンに変わります。  
  
2.  クリックし、マウスの左ボタンを押したままおよび上または下に、ウィンドウの端をドラッグします。  
  
     メイン編集ウィンドウ全体を垂直方向にサイズ変更することにより、スキーマ ツリー ビューおよびグリッド ビューを垂直方向にサイズ変更できます。  
  
### <a name="to-make-the-schema-tree-views-or-the-grid-view-wider-or-more-narrow"></a>スキーマ ツリー ビューまたはグリッド ビューを水平方向にサイズ変更するには  
  
1.  標準的なウィンドウの水平方向サイズ変更アイコンにカーソルが変更されるまで (それらの間、グリッド ビューから、スキーマ ツリー ビューで除算) をメイン編集ウィンドウの 2 つのペインの仕切りのいずれかにマウス ポインターを移動します。  
  
2.  マウスの左ボタンをクリックし、ボタンを押しながらペインの端を左 (狭くする) または右 (広くする) にドラッグします。  
  
     メイン編集ウィンドウ内で 1 つのスキーマ ツリー ビューとグリッド ビューが占める割合を水平方向に変更することにより、これらのビューを水平方向にサイズ変更できます。  
  
     また、メイン編集ウィンドウ全体を水平方向にサイズ変更する方法で、スキーマ ツリー ビューとグリッド ビューを水平方向にサイズ変更することもできます。  
  
## <a name="remembering-the-current-view-of-mapper"></a>マッパーの現在のビューの記憶  
 BizTalk マッパーでは、拡大レベルやユーティリティ リボン オプションのオン/オフ状態、リンク/Functoid の現在の配置などすべての設定が記憶されます。  
  
> [!NOTE]
>  BizTalk プロジェクトやソリューションに複数のマップが含まれる場合は、マップごとに詳細設定が記憶されます。  
  
> [!CAUTION]
>  前のビューの設定が格納されている、  **\*.suo**ファイル。 このファイルを Visual Studio のプロジェクト フォルダーから削除しないようにしてください。  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパー コマンドを使用します。](../core/using-biztalk-mapper-commands.md)   
 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)   
 [選択したマップ項目をビュー内に置く方法](../core/how-to-bring-selected-map-items-in-view.md)   
 [スキーマ ツリー ビューを最適化する方法](../core/how-to-optimize-the-schema-tree-view.md)