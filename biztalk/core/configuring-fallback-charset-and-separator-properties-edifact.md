---
title: "フォールバック文字セットと区切り記号 (EDIFACT) のプロパティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9eadc9c1-ebec-42f5-a9ca-06cb28bebcdf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b517a98130f2d245d68083dc16c65865950800c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-charset-and-separator-properties-edifact"></a>フォールバック文字セットと区切り記号のプロパティの構成 (EDIFACT)
フォールバック アグリーメントでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、送信 EDIFACT メッセージのエンベロープを作成するときにパーティのプロパティを検証するために使用する文字セット (UNA) を指定できます。 インターチェンジのセグメントに使用する区切り記号と終端記号 (UNB) も指定できます。  
  
 UNA セグメントでは、BizTalk Server がパーティに送信する EDIFACT エンコード インターチェンジの UNA セグメントをどのように生成するかを定義します。 UNA セグメントでは、EDIFACT エンコード インターチェンジの区切り記号およびインジケータとして使用される文字を定義します。 標準以外の区切り文字がインターチェンジに含まれている場合にのみ、このセグメントを使用します。  
  
 UNB セグメントでは、使用する EDIFACT 文字セットを定義します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-character-set-and-separators"></a>文字セットと区切り記号を構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**パーティ**ノードをクリックして**EDIFACT フォールバックの設定**です。  
  
2.  **EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**文字セットと区切り記号**です。  
  
3.  **構文 (UNB1)**セクションで、次の操作します。  
  
    1.  **識別子 (UNB1.1)**、送信インターチェンジに適用される設定の EDIFACT 文字を入力します。 このフィールドは必須です。  
  
    2.  **バージョン (UNB1.2)**、間の値を選択して**1**と**4**です。 このフィールドの入力は省略可能です。  
  
4.  **区切り記号**セクションで、次の操作します。  
  
    1.  **コンポーネント データ要素区切り記号 (UNA1)**、複合データ要素内の単純データ要素を区切るコンポーネント データ要素区切り記号の値を入力します。 選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。 文字の書式を変更すると、入力した文字が自動的に変更されます。  
  
    2.  **データ要素区切り記号 (UNA2)**、2 つ以上の単純データ要素または複合型の一部ではない単純データ要素から成る複合データ要素を区切るデータ要素区切り記号の値を入力します。 選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。 文字の書式を変更すると、入力した文字が自動的に変更されます。  
  
    3.  **小数点表記 (UNA3)**、送信インターチェンジで使用される 10 進表記法を選択します。  
  
    4.  **リリース インジケータ (UNA4)**、直後の文字が構文区切り文字、終端記号、またはリリース文字ではなく、元のデータの一部であることを示すリリース インジケーターの値を入力します。 選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。 文字の書式を変更すると、入力した文字が自動的に変更されます。  
  
    5.  **繰り返し区切り記号 (UNA5)**を区切るために使用される繰り返し区切り記号は、トランザクション セット内で繰り返すをセグメントの値を入力します。 選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。 文字の書式を変更すると、入力した文字が自動的に変更されます。  
  
    6.  **セグメント終端記号 (UNA6)**、EDI セグメントの末尾を示すセグメント終端記号の値を入力します。  
  
    7.  **UNA6 サフィックス**、BizTalk Server がセグメント識別子を使用するか、使用する文字を選択して**None**、 **CR** (復帰)、 **LF**(改行)、または**CR LF** (キャリッジ リターン/ライン フィード) です。 サフィックスを指定した場合は、セグメント終端記号データ要素を空白にすることができます。 セグメント終端記号を空白のままにした場合は、サフィックスを指定する必要があります。 セグメント終端記号とサフィックスの組み合わせとして、次の値のいずれかを指定できます。  
  
        -   [ セグメント終端記号]  
  
        -   セグメント終端記号 + 復帰  
  
        -   セグメント終端記号 + 復帰/改行  
  
        -   キャリッジ リターン  
  
        -   ライン フィード  
  
        -   キャリッジ リターン/ライン フィード  
  
5.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を検証し、変更を確定し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理に対する EDIFACT フォールバック アグリーメントのプロパティを構成します。](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)