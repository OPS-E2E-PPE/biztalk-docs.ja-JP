---
title: "オプションの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f4b0b51-2cad-4cb5-b6cd-4db92bd199fa
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b19646c9c83eff4a3171b4d25763a6b581d45b1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="optional-configurations"></a>オプションの構成
BizTalk Server 管理パックをインポートした後、[監視] ウィンドウのナビゲーション ウィンドウには、自動的に検出されるオブジェクトの種類が表示されます。 オブジェクトの種類の一覧は、次を参照してください。[管理パックで検出されるオブジェクト](../technical-guides/objects-the-management-pack-discovers.md)セクションです。 によって検出されるオブジェクトの既定の検出構成を変更することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パック。 構成設定を変更するのにには、Operations Manager 2007 R2 または 2012 の上書き機能を使用します。  
  
 自動的に検出されていないオブジェクトの種類の自動検出の設定を有効にできます、 **Authoring**オペレーション コンソール ウィンドウ。  
  
#### <a name="to-use-an-override-to-change-the-setting-for-automatic-discovery"></a>上書きを使用して自動検出の設定を変更するには  
  
1.  作成 ウィンドウで **管理パック オブジェクト**、順にクリック**オブジェクト検出**です。  
  
2.  Operations Manager ツールバーで、をクリックして**スコープ**、および BizTalk Server のオブジェクトのみを含めるには、詳細ウィンドウに表示されているオブジェクトをフィルター処理します。  
  
3.  詳細ウィンドウでの設定を変更するオブジェクトの種類をクリックします。  
  
4.  Operations Manager ツールバーで、をクリックして**オーバーライド**をクリックして**オブジェクト検出の上書き**、いずれかをクリックして**型のすべてのオブジェクト:** \< *オブジェクトの種類の名前*\>、**グループの特定のオブジェクト型の場合:** \<*オブジェクトの種類の名前*\>、または**別の型のすべてのオブジェクト**です。  
  
5.  **上書きのプロパティ**ダイアログ ボックスで、をクリックして、**オーバーライド**のボックス、**有効**パラメーターを変更します。  
  
6.  [**管理パック**、] をクリックして**新規**管理パックの封印されていないバージョンを作成し、をクリックして**OK**です。  
  
 上書きの設定を変更すると、オブジェクトの種類が自動的に検出し、[監視] ウィンドウで表示されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
 設定の上書きについては、次を参照してください。 [Operations Manager 2007 R2 または 2012 よりも優先](http://go.microsoft.com/fwlink/?LinkId=86870)(http://go.microsoft.com/fwlink/?LinkId=86870)。