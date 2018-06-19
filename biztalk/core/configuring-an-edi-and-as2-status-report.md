---
title: EDI および AS2 状態レポートの構成 |Microsoft ドキュメント
description: 作成、EDI または AS2 状態レポート クエリ式、および BizTalk Server でのレポートに表示されているデータを選択
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6490864d-f1e6-4932-aefb-c332a595aad7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 833e3c6c26cdac57d7cc57d828b66a66b9eb37f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233682"
---
# <a name="configure-an-edi-and-as2-status-report"></a>EDI および AS2 状態レポートを構成します。
EDI を有効にするか、状態レポートを表示する AS2 状態レポートを後から、使用する、 **EDI 状態レポート**または**EDIINT 状態レポート**のセクションで、**グループ ハブ**タブ、**グループの概要** ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 状態レポートを表示するときに、データの既定のセットが表示されます。 状態レポートの次の要素を構成できます。  
  
-   たとえば、日付の範囲、データの方向 (受信または送信)、状態の値 (受理、拒否、すべてなど) などの、状態レポートの対象となるデータの範囲を決定するために実行されるクエリ式。  
  
-   レポートのデータ列に基づいて決定される、状態レポート ペインに表示されるデータの種類。  
  
    > [!NOTE]
    >  状態レポートが有効になっている場合、常にすべての状態がストレージに保存されます。 クエリ式または状態列をカスタマイズすることで、表示する保存データを定義します。  
  
 5 つの異なる EDI および AS2 状態レポートを利用できます (を参照してください[型の EDI および AS2 状態レポート](../core/types-of-edi-and-as2-status-reports.md))。 レポートのデータが異なっていても、レポートを構成する方法は同じです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
## <a name="configure-the-status-report-query-expression"></a>ステータス レポートのクエリ式を構成します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、 **BizTalk グループ**を表示するノード、**グループの概要**ウィンドウです。  
  
2.  下部にある、**グループ ハブ** タブで、**グループの概要** ウィンドウで、状態レポートなど、構成する をクリックして**EDI インターチェンジと関連する ACK の状態**です。  
  
3.  **クエリ式**状態レポート ペインの領域は、クエリを定義するすべてのフィルター条件が存在することを確認します。 いない場合は、空の行で下矢印をクリックして、**フィールド名**フィルター条件をクエリ式を追加するをクリックし、クエリ式の下部にある列です。 フィルター条件の行を削除するには、行を選択しをクリックすると、**削除**キーボードのボタンをクリックします。  
  
4.  フィルタ式の値が適切かどうか確認します。 いない場合は、下矢印をクリックして、**演算子**をクエリ操作を選択し、適切な値を入力列、**値**列です。  
  
    > [!NOTE]
    >  演算子とのクエリ式のフィルタ条件として使用可能な値に記載されて[型の EDI および AS2 状態レポート](../core/types-of-edi-and-as2-status-reports.md)と**EDI AS2 状態レポート UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
5.  フィルター条件に従った状態レポートを表示する、クエリを実行する をクリックして**クエリの実行**です。  
  
6.  クエリ式を .btq ファイルとして保存する] をクリックして**名前を付けて保存**フォルダーを指定し、ファイル名を入力し、[クリックして**保存**です。  
  
7.  保存されている .btq ファイルを開くにはクリックして**クエリを開く**です。  
  
## <a name="configure-the-type-of-data-displayed-in-the-status-report-pane"></a>状態レポート ペインに表示されるデータの種類を構成します。  
  
1.  状態レポート ペインの状態の結果領域を右クリックし、をクリックして**列の追加/削除**です。  
  
2.  表示されている列の一覧に状態カテゴリを追加するには、内の列をクリックして、**使用可能な列**一覧をクリックして**追加**です。  
  
3.  表示されている列の一覧から状態カテゴリを削除するには、内の列をクリックして、**表示されている列**一覧をクリックして**削除**です。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)   
 [EDI および AS2 状態レポートを有効にします。](../core/enabling-edi-and-as2-status-reports.md)   
 [EDI または AS2 状態レポートを表示します。](../core/displaying-an-edi-or-as2-status-report.md)