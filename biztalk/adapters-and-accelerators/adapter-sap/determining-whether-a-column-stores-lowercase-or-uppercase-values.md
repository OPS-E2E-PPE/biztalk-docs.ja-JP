---
title: 列が小文字または大文字の値を格納するかどうかを決定する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1edc8332-d8c7-4040-895b-f121fb03df44
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a457ddbde4a6a1dcfa3b4d2c4f818d01dcae009
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373525"
---
# <a name="determining-whether-a-column-stores-lowercase-or-uppercase-values"></a>列ストアの小文字または大文字の値かどうかを決定します。
このセクションでは、SAP テーブル内の列が小文字または大文字の文字を保存するかどうかを確認するための SAP システムで実行する高度なタスクが一覧表示します。 このタスクを実行する方法の詳細な手順については、SAP 管理者に問い合わせるか、SAP のマニュアルを参照してくださいする必要があります。  
  
### <a name="to-determine-the-case-of-values-stored-in-a-column"></a>列に格納されている値の大文字と小文字を決定するには  
  
1.  SAP GUI を起動します。  
  
2.  トランザクション SE37 に移動し、DDIF_TABL_GET を実行します。  
  
3.  NAME パラメーターの文字の大文字と小文字の情報を決定する列を含むテーブル名を指定します。 たとえば、KNA1 です。  
  
4.  テーブルの最初のパラメーターは、DD03P_TAB です。 テーブルの行を表示するパラメーターをクリックします。 このテーブル内のすべての行が列に対応手順 3. で指定した (KNA1) などの表にします。  
  
5.  DD03P_TAB で行ごとに小文字の列の値を探します。 小文字の列の値が 'X'、KNA1) などのテーブルの対応する列の場合は、大文字と小文字の両方を格納できます。 小文字の列の値が空の場合、対応する列は大文字の文字をのみ格納できます。  
  
     たとえば、名前の行、小文字列は X です。そのため、KNA1 [名前] 列には、大文字と小文字の両方の文字を格納できます。 ただし、小文字 LAND1 行の列が空です。 そのため、KNA1 テーブル内の LAND1 列は文字の大文字のみ格納できます。  
  
## <a name="see-also"></a>参照  
 [特定の SAP アダプターのシナリオを SAP GUI を使用したタスクを実行します。](../../adapters-and-accelerators/adapter-sap/performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)