---
title: "列が大文字か小文字の値を格納するかどうかを決定する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1edc8332-d8c7-4040-895b-f121fb03df44
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b54c00b43192462fb095dbfbfda4cbf0b248a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="determining-whether-a-column-stores-lowercase-or-uppercase-values"></a>列ストアの小文字または大文字の値かどうかを決定します。
このセクションでは、SAP テーブル内の列が小文字または大文字の文字を格納するかどうかを決定する SAP システム上で実行される高度なタスクを一覧表示します。 このタスクを実行する方法の詳細な手順については、SAP 管理者に問い合わせるか、SAP のマニュアルを参照してください必要があります。  
  
### <a name="to-determine-the-case-of-values-stored-in-a-column"></a>列に格納された値の大文字と小文字を決定するには  
  
1.  SAP の GUI を起動します。  
  
2.  トランザクション SE37 を開き、DDIF_TABL_GET を実行します。  
  
3.  NAME パラメーターの文字の小文字の情報を確認する列を含むテーブル名を指定します。 たとえば、KNA1 です。  
  
4.  テーブルの最初のパラメーターは、DD03P_TAB です。 テーブル内の行を表示するパラメーターをクリックします。 このテーブルのすべての行が列に対応手順 3. で指定した (KNA1) などの表にします。  
  
5.  DD03P_TAB での行ごとに小文字の列の値を探します。 小文字の列の値が 'X'、KNA1) などのテーブルの対応する列の場合は、大文字と小文字の両方を格納できます。 小文字の列の値が空の場合は、対応する列は大文字の文字をのみ格納できます。  
  
     たとえば、小文字の名前の行の列は X です。そのため、KNA1 [名前] 列には、大文字と小文字の両方を格納できます。 ただし、小文字 LAND1 行の列が空です。 そのため、LAND1 KNA1 のテーブル列には、大文字の文字をのみ格納できます。  
  
## <a name="see-also"></a>参照  
 [特定の SAP アダプターのシナリオを SAP GUI を使用したタスクを実行します。](../../adapters-and-accelerators/adapter-sap/performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)