---
title: SAP クエリのパラメーターを BizTalk での mySAP アダプターでの EXECQUERY コマンドに変換 |Microsoft Docs
description: 例を含む、EXECQUERY に SAP クエリを変換するためのガイダンス
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
ms.openlocfilehash: c8ffd480e952e0df7114a93f6cb2a5baf631ad96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021697"
---
# <a name="translate-sap-query-parameters-into-execquery-command"></a>SAP クエリのパラメーターを EXECQUERY コマンドに変換します。
クエリのパラメーターを EXECQUERY コマンド テキストに変換する方法について説明します。 このトピックでは、ZQUERY_TST_NEW カスタムの SAP クエリの例を使用します。  
  
## <a name="open-the-query-in-sap-gui"></a>SAP の GUI でクエリを開く  
 SAP でクエリを開くには、次の手順を実行します。 ここで示す手順では、ZQUERY_TST_NEW クエリはされ、SAP のバージョンに固有です。  
  
1. SQ01 トランザクションを実行します。  
  
2. **ユーザー グループからクエリ**] ページで [**クイック ビューアー**します。  
  
3. **クイック ビューアー**  ページの 、**簡易ビュー**テキスト ボックスに「 `ZQUERY_TST_NEW`、 をクリックし、**表示**します。  
  
4. **クイック ビューアー**  ページで、をクリックして、**選択フィールド** タブをクエリのすべてのパラメーターを一覧表示します。  
  
    次の図は、クエリ定義にすべてのパラメーターを示します。  
  
    ![SAP クエリのパラメーターのリスト](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")  
  
5. **[実行]** をクリックします。 次のページが表示されます。  
  
    ![SAP クエリのパラメーター値を指定](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")  
  
6. 各パラメーターを定義する黄色の矢印をクリックします。 特定の許容/非の許容値を定義するか、または許容/非の許容値の範囲を定義することができます。  EXECQUERY 構文は、パラメーターごとに、SAP GUI で構成されている値に基づいて指定する必要があります。  
  
   次のセクションでは、SAP GUI で値を定義する方法と、それらの値が EXECQUERY 構文に変換する方法について説明します。  
  
## <a name="frame-an-execquery-syntax"></a>フレーム、EXECQUERY 構文  
 ようになります EXECQUERY 構文は、クエリ定義で定義されているパラメーターの値に基づいて何を見てみましょう。 これを理解する最初のパラメーターの値を構成する方法の例を紹介します**2 桁の数字**、翻訳、 **ZQUERY_TST_NEW**クエリ。  
  
 最初に、仮定の値、 **vals をシングル**(緑色のドット) を持つタブは次のスクリーン ショットに示すように定義されます。  
  
 ![クエリが実行できるパラメーター値の一覧](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")  
  
> [!NOTE]
>  に対しては、黄色の矢印をクリックした後、このダイアログ ボックスが表示されます、 **2 桁の数字**パラメーター。  
  
 このような場合は、EXECQUERY 構文はようになります。  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5'  
```  
  
 内の値だけでなく、同じクエリに対して、 **vals をシングル** タブ (緑の丸印が付きます) を用意することも、値、 **vals シングル**次として定義されています (赤色のドット) を含むタブ。  
  
 ![クエリを使用できないパラメーター値の一覧](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")  
  
 このような場合は、EXECQUERY 構文はようになります。  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8'  
```  
  
 ここでは、値を追加する場合、**範囲**(緑の丸印が付きます)、このようなタブの次のスクリーン ショットします。  
  
 ![クエリが実行できるパラメーター値の範囲](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")  
  
 EXECQUERY 構文ようになります。  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5'  
```  
  
 同様に、値を追加する場合、**範囲**ようなタブ (の赤色のドット)、次のスクリーン ショットに示すように。  
  
 ![クエリを使用できないパラメーター値の範囲](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")  
  
 EXECQUERY 構文ようになります。  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5', NOT @P1 BETWEEN '6' AND '8'  
```  
  
 シンプルさとについては、このトピックでのみについて説明、最初のパラメーター **2 桁の数字**します。 同様のメソッドを使用すると、他のパラメーターに対して定義されている値を EXECQUERY 構文に変換する方法を決定します。  
  
