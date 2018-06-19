---
title: スキーマを置換する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 104e60d3-1303-4e56-b13a-c10ab14ba383
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df444b8169d75408fe6e412135029ae2b051a6d2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25972632"
---
# <a name="how-to-replace-schemas"></a>スキーマを置換する方法
更新されたスキーマを取引先から受け取った場合など、既存のマップ内にある送信元や送信先スキーマの置換が必要になることがあります。  
  
> [!NOTE]
>  BizTalk マッパーでは、保持されるスキーマと置換されるスキーマの間の既存のリンクが維持されます。  
  
## <a name="replace-a-source-or-destination-schema"></a>送信元または送信先スキーマを置換します。  
  
1.  移行元または送信先のスキーマ ツリー ビューを右クリックし、 **スキーマの置換**します。  
  
    > [!NOTE]
    >  または、キーボードで Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら S キーを押します。 マッパーのキーボード ショートカットの一覧については、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
2.  **BizTalk 型の選択** ] ダイアログ ボックスで、展開、 **スキーマ** 、ツリー内のノードが、適切なスキーマを選択し、[ **OK**します。  
  
     ![スキーマを選択](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")  

    > [!TIP] 
    > **以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** スキーマの完全な名前を表示する型の選択 ウィンドウのサイズを変更することができます。
      
     置換スキーマに単一のルートが存在するか、置換を使用してスキーマのルート ノードが設定された場合のみ、 **ルート参照** のプロパティ、 **スキーマ** ノード、該当するペインに置換スキーマが開きますおよび手順 3. を実行する必要はありません。  
  
3.  複数のルート ノードが、送信先スキーマ内に存在し、変換先を使用してスキーマのルート ノードが設定されていない場合、**ルート参照**のプロパティ、**スキーマ**ノードで、**ルートノードを\<*ソース/ターゲット*\>スキーマ**ダイアログ ボックスで、適切なルート ノードを選択し、 **OK**です。  
  
     該当するペインに置換スキーマが開きます。  
  
    > [!NOTE]
    >  スキーマを置換する際、関連するレコードまたはフィールドが見つかった場合は、一部のリンクが失われる可能性があります。 選択した場合にのみ、スキーマが置き換えられます **はい** で、 **確認**   ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のマップの管理](../core/managing-maps-within-projects.md)