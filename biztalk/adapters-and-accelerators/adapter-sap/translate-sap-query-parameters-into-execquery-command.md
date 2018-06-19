---
title: SAP クエリのパラメーターを BizTalk での mySAP アダプターで EXECQUERY コマンドに変換 |Microsoft ドキュメント
description: EXECQUERY、例と共に SAP クエリを変換するガイダンス
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a545e20-2607-4946-a60d-0a227b86d093
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efb50db3e499970c0504f81467d382aee31c868f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217730"
---
# <a name="translate-sap-query-parameters-into-execquery-command"></a>SAP クエリのパラメーターを EXECQUERY コマンドに変換します。
クエリのパラメーターが EXECQUERY コマンド テキストに変換する方法について説明します。 このトピックでは、ZQUERY_TST_NEW カスタムの SAP クエリの例を使用します。  
  
## <a name="open-the-query-in-sap-gui"></a>SAP の GUI でクエリを開く  
 SAP でクエリを開くには、次の手順を実行します。 ここで示す手順では、ZQUERY_TST_NEW クエリに対してはされ、SAP のバージョンに固有です。  
  
1.  SQ01 トランザクションを実行します。  
  
2.  **ユーザー グループからクエリ**] ページで [**クイック ビューアー**です。  
  
3.  **クイック ビューアー** ] ページの [、**簡易ビュー**テキスト ボックスで、「 `ZQUERY_TST_NEW`、クリックしてして**表示**です。  
  
4.  **クイック ビューアー**  ページで、をクリックして、**選択フィールド**タブは、クエリ内のすべてのパラメーターを一覧表示します。  
  
     次の図は、クエリ定義にすべてのパラメーターを示します。  
  
     ![SAP クエリのパラメーターのリスト](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")  
  
5.  **[実行]** をクリックします。 次のページが表示されます。  
  
     ![SAP クエリのパラメーター値を指定](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")  
  
6.  各パラメーターを定義する黄色の矢印をクリックします。 特定の許容/非で許容される値を定義するか、または許容/非-許容値の範囲を定義することができます。  パラメーターごとに、SAP GUI で構成されている値に基づいて EXECQUERY 構文を指定する必要があります。  
  
 次のセクションでは、SAP GUI での値を定義する方法と、それらの値が EXECQUERY 構文に変換する方法について説明します。  
  
## <a name="frame-an-execquery-syntax"></a>フレーム EXECQUERY 構文  
 新機能のようになります EXECQUERY 構文に基づいてクエリ定義で定義されているパラメーター値を見てみましょう。 これを理解するには、最初のパラメーターの値を構成する方法の例について説明します**2 桁の数字**、翻訳、 **ZQUERY_TST_NEW**クエリ。  
  
 最初に、仮定の値、 **vals を単一**(緑色のドット) のタブは、次のスクリーン ショットに示すように定義されているは。  
  
 ![クエリに使用できるパラメーター値の一覧](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")  
  
> [!NOTE]
>  に対して、黄色の矢印をクリックした後、このダイアログ ボックスが表示されます、 **2 桁の数字**パラメーター。  
  
 このような場合は、EXECQUERY 構文はようになります。  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5'  
```  
  
 内の値だけでなく、同じクエリに対して、 **vals を単一** タブ (緑ピリオドの場合) にすることもできます値、 **vals を単一**は次のように定義されている (赤色のドット) を持つタブ。  
  
 ![クエリがとることのできないパラメーター値の一覧](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")  
  
 このような場合は、EXECQUERY 構文はようになります。  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8'  
```  
  
 ここでは、値を追加する場合、**範囲**(緑ドットの場合) のようなタブの次のスクリーン ショットします。  
  
 ![クエリに使用できるパラメーター値の範囲](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")  
  
 EXECQUERY 構文は、ようになります。  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5'  
```  
  
 同様に、値を追加する場合、**範囲**(赤色のドット) を持つ タブのような次のスクリーン ショットに示すように。  
  
 ![クエリがとることのできないパラメーター値の範囲](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")  
  
 EXECQUERY 構文は、ようになります。  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5', NOT @P1 BETWEEN '6' AND '8'  
```  
  
 簡潔さとについては、このトピックの内容のみについて説明、最初のパラメーター **2 桁の数字**します。 その他のパラメーターに対して定義された値が EXECQUERY 構文に変換する方法を決定するのに同様のメソッドを使用できます。  
  
