---
title: EDI および AS2 状態レポートの構成 |Microsoft Docs
description: 作成、EDI または AS2 状態レポートのクエリ式、および BizTalk Server でのレポートに表示されているデータを選択
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
ms.openlocfilehash: ce12c33570189f8436752d1741957f51779d25d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391366"
---
# <a name="configure-an-edi-and-as2-status-report"></a>EDI および AS2 状態レポートを構成します。
EDI を有効にするか、状態レポートを表示するために AS2 状態レポートを後から必要な**EDI 状態レポート**または**EDIINT 状態レポート**のセクション、**グループ ハブ**タブ、**グループの概要**ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 状態レポートを表示する場合、既定値が表示されますデータのセット。 状態レポートの次の側面を構成することができます。  
  
- 状態の報告、たとえばデータ、日付範囲、データの方向の範囲を決定するために実行するクエリ式 (受信または送信)、または状態の値 (受理、拒否、すべてなど)  
  
- レポート内のデータ列によって決定される、状態レポート ペインに表示されるデータの型。  
  
  > [!NOTE]
  >  状態レポートが有効になっているときにすべての状態は記憶域に保存されます。 クエリ式または状態列をカスタマイズするとは、表示する保存されたデータを定義します。  
  
  5 つのさまざまな EDI および AS2 状態レポートが利用可能な (を参照してください[型の EDI および AS2 状態レポート](../core/types-of-edi-and-as2-status-reports.md))。 各レポートを構成する方法は、各レポートのデータが異なる場合でも、同じです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
## <a name="configure-the-status-report-query-expression"></a>状態レポートのクエリ式を構成します。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、 **BizTalk グループ**ノードを表示、**グループの概要**ウィンドウ。  
  
2. 下部にある、**グループ ハブ** タブで、**グループの概要**ウィンドウで、状態レポートなど、構成する をクリックして**EDI インターチェンジと関連する ACK の状態**します。  
  
3. **クエリ式**状態レポート ペインの領域では、クエリを定義するすべてのフィルター条件が存在することを確認します。 そうでない場合に空の行で下矢印をクリックします。、**フィールド名**クエリ式、およびフィルター クエリ式に追加する条件をすべて選択 の下部にある列です。 フィルター条件の行を削除するには、行を選択し、クリックすると、**削除**キーボードのキー。  
  
4. 確認としてフィルター式の値が目的です。 そうでない場合は、の下矢印をクリックして、**演算子**を、クエリ操作を選択し、適切な値を入力列、**値**列。  
  
   > [!NOTE]
   >  演算子およびクエリ式でフィルター条件の使用可能な値については説明[型の EDI および AS2 状態レポート](../core/types-of-edi-and-as2-status-reports.md)と**EDI AS2 状態レポート UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  
  
5. フィルターの条件に従った状態レポートを表示する、クエリを実行する をクリックして**クエリの実行**します。  
  
6. クエリ式を .btq ファイルとして保存する をクリックして**付けて**、フォルダーを指定し、ファイル名を入力して順にクリックします**保存**します。  
  
7. 保存されている .btq ファイルを開くには、次のようにクリックします。**クエリを開く**します。  
  
## <a name="configure-the-type-of-data-displayed-in-the-status-report-pane"></a>状態レポート ペインに表示されるデータの種類を構成します。  
  
1.  状態レポート ペインの状態の結果の領域を右クリックし、をクリックし、**列の追加/削除**します。  
  
2.  表示されている列の一覧には、状態のカテゴリを追加するで列をクリックします。、**使用可能な列**ボックスの一覧をクリック**追加**します。  
  
3.  表示されている列の一覧から状態カテゴリを削除するで列をクリックします。、**表示されている列**ボックスの一覧をクリック**削除**します。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)   
 [EDI および AS2 状態レポートを有効にします。](../core/enabling-edi-and-as2-status-reports.md)   
 [EDI または AS2 状態レポートの表示](../core/displaying-an-edi-or-as2-status-report.md)