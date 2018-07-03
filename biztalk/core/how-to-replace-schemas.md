---
title: スキーマを置換する方法 |Microsoft Docs
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
ms.openlocfilehash: f8aaca705c54866ec6323d7c26a5fe7b731129e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022528"
---
# <a name="how-to-replace-schemas"></a>スキーマを置換する方法
更新されたスキーマを取引先から受け取った場合など、既存のマップ内にある送信元や送信先スキーマの置換が必要になることがあります。  
  
> [!NOTE]
>  BizTalk マッパーでは、保持されるスキーマと置換されるスキーマの間の既存のリンクが維持されます。  
  
## <a name="replace-a-source-or-destination-schema"></a>送信元または送信先スキーマを置換します。  
  
1. 移行元または送信先のスキーマ ツリー ビューを右クリックし、**スキーマの置換**します。  
  
   > [!NOTE]
   >  または、キーボードで Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら S キーを押します。 マッパーのキーボード ショートカットの完全な一覧を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)します。  
  
2. **BizTalk 型の選択**] ダイアログ ボックスで、展開、**スキーマ**ツリーで、ノードは、適切なスキーマを選択し、[ **OK**します。  
  
    ![スキーマ選択](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")  

   > [!TIP]
   > **以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** スキーマの完全名を表示する型の選択 ウィンドウのサイズを変更することができます。
      
    場合のみ、置換スキーマに単一のルートが存在するか、使用して置換スキーマのルート ノードが設定された、**ルート参照**のプロパティ、**スキーマ**ノード、置換スキーマが開きます関連するウィンドウで、手順 3. を実行する必要はありません。  
  
3. 複数のルート ノードが、送信先スキーマ内に存在し、使用して変換先スキーマのルート ノードが設定されていない場合、**ルート参照**のプロパティ、**スキーマ**ノードで、**ルートノードの\<*ソース/ターゲット*\>スキーマ**ダイアログ ボックスで、適切なルート ノードを選択し、 **OK**します。  
  
    該当するペインに置換スキーマが開きます。  
  
   > [!NOTE]
   >  スキーマを置換する際、関連するレコードまたはフィールドが見つかった場合は、一部のリンクが失われる可能性があります。 選択した場合にのみ、スキーマが置き換えられます**はい**上、**確認** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のマップの管理](../core/managing-maps-within-projects.md)