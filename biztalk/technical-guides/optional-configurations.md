---
title: オプションの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f4b0b51-2cad-4cb5-b6cd-4db92bd199fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1ee8c10485522db82040210eff2a7afbc785d25
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992467"
---
# <a name="optional-configurations"></a>オプションの構成
BizTalk Server 管理パックをインポートした後、[監視] ウィンドウのナビゲーション ウィンドウが自動的に検出されるオブジェクトの種類が表示されます。 オブジェクトの種類の一覧は、次を参照してください。 [、管理パックで検出されるオブジェクト](../technical-guides/objects-the-management-pack-discovers.md)セクション。 によって検出されるオブジェクトの既定の検出構成を変更することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パック。 Operations Manager 2007 R2 または 2012 の上書き機能を使用して、構成設定を変更します。  
  
 自動的に検出されていないオブジェクトの種類を [自動検出の設定を有効にできます、 **Authoring**オペレーション コンソール] ウィンドウ。  
  
#### <a name="to-use-an-override-to-change-the-setting-for-automatic-discovery"></a>上書きを使用して自動検出の設定を変更するには  
  
1. 作成 ウィンドウで、展開**管理パック オブジェクト**、順にクリックします**オブジェクト検出**します。  
  
2. Operations Manager ツールバーで、次のようにクリックします。**スコープ**、BizTalk Server オブジェクトだけが詳細ウィンドウに表示されるオブジェクトをフィルターします。  
  
3. 詳細ペインでの設定を変更するオブジェクトの種類をクリックします。  
  
4. Operations Manager ツールバーで、次のようにクリックします**オーバーライド**、 をクリック**オブジェクト検出の上書き**、 をクリックし、**型のすべてのオブジェクト:** \<  *。オブジェクトの種類の名前*\>、**グループの種類の特定のオブジェクトの場合:** \<*オブジェクトの種類の名前*\>、または**別の型のすべてのオブジェクト**します。  
  
5. **上書きのプロパティ**ダイアログ ボックスで、をクリックして、**オーバーライド**のボックス、**有効**パラメーターを変更します。  
  
6. [**管理パック**、] をクリックして**新規**をクリックして、管理パックの封印されていないバージョンを作成**OK**します。  
  
   上書きの設定を変更すると、オブジェクトの種類が自動検出し、[監視] ウィンドウで表示されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
   上書きの設定方法の詳細については、次を参照してください。 [Operations Manager 2007 R2 または 2012 オーバーライド](http://go.microsoft.com/fwlink/?LinkId=86870)(http://go.microsoft.com/fwlink/?LinkId=86870)します。