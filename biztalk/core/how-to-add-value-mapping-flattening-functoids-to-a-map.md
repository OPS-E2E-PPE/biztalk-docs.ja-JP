---
title: 値のマッピング (フラット化) Functoid をマップに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00a447c3-58d0-42ab-a5c4-417ee7800a6b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b630b586e1252d0afb244deb77ab3e4c7bfaf30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343056"
---
# <a name="how-to-add-value-mapping-flattening-functoids-to-a-map"></a>値のマッピング (フラット化) Functoid をマップに追加する方法
**値のマッピング (フラット化)** functoid では、複数のレコードを 1 つのレコードに変換することによって、入力インスタンス メッセージの一部をフラット化することができます。 これは、Microsoft Commerce Server カタログを変換する場合の一般的な操作です。  
  
 概念情報については、**値のマッピング (フラット化)** functoid を参照してください[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)します。  
  
### <a name="to-add-the-value-mapping-flattening-functoid-to-a-map-and-configure-it"></a>値のマッピング (フラット化) functoid をマップに追加し、構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  
  
    選択したカテゴリでの高度な functoid の一覧が表示されます。  
  
2. ドラッグ、**値のマッピング (フラット化)** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) ツールボックスからグリッド ページの適切な場所にします。  
  
   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。  
  
   > [!NOTE]
   >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3. 最初の入力パラメーターを設定する、**値のマッピング (フラット化)** functoid をドラッグして、入力リンクを作成、**値のマッピング (フラット化)** ソースのレコードまたはフィールド ノードを functoidスキーマ、またはブール型のデータ型を持つ別の functoid の左側に、および"true"または"false"の入力値が生成されます  
  
   > [!NOTE]
   >  ドラッグすることも、方向が逆にするブール値のソースをドラッグ、**値のマッピング (フラット化)** functoid。  
  
4. 2 番目の入力パラメーターを設定する、**値のマッピング (フラット化)** functoid をドラッグして、入力リンクを作成、**値のマッピング (フラット化)** ソースのレコードまたはフィールド ノードを functoidスキーマ、送信元スキーマのレコードまたはフィールド ノードをドラッグするか、**値のマッピング (フラット化)** functoid、または定数を挿入します。  
  
   > [!NOTE]
   >  2 番目の入力パラメーターを**値のマッピング (フラット化)** の左側に、functoid は別の functoid の出力から指定もできます。 リンクを作成して、表すなどのソースの関連する functoid のいずれかをその他の関連する functoid にドラッグして入力します。  
  
5. 出力パラメーターを使用する、**値のマッピング (フラット化)** functoid をドラッグして、出力リンクを作成、**値のマッピング (フラット化)** のレコードまたはフィールドを送信先スキーマ、または functoid変換先スキーマのレコード フィールドをドラッグして、**値のマッピング (フラット化)** functoid。  
  
   > [!NOTE]
   >  他の functoid の出力と同様、**値のマッピング (フラット化)** functoid を別の functoid への入力として使用できます。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)