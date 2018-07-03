---
title: フォールバック文字セットと区切り記号 (EDIFACT) のプロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9eadc9c1-ebec-42f5-a9ca-06cb28bebcdf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8d36df63d1bcad0ebd39bd828a1a9407e6cc480
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977107"
---
# <a name="configuring-fallback-charset-and-separator-properties-edifact"></a>フォールバック文字セットと区切り記号のプロパティの構成 (EDIFACT)
フォールバック アグリーメントでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、送信 EDIFACT メッセージのエンベロープを作成するときにパーティのプロパティを検証するために使用する文字セット (UNA) を指定できます。 インターチェンジのセグメントに使用する区切り記号と終端記号 (UNB) も指定できます。  
  
 UNA セグメントでは、BizTalk Server がパーティに送信する EDIFACT エンコード インターチェンジの UNA セグメントをどのように生成するかを定義します。 UNA セグメントは、EDIFACT エンコード インターチェンジの区切り記号およびインジケータとして使用される文字を定義します。 標準以外の区切り文字がインターチェンジに含まれている場合にのみ、このセグメントを使用します。  
  
 UNB セグメントでは、使用する EDIFACT 文字セットを定義します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-character-set-and-separators"></a>文字セットと区切り記号を構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**EDIFACT フォールバックの設定**します。  
  
2. **EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**文字セットと区切り記号**します。  
  
3. **構文 (UNB1)** セクションで、次の操作を行います。  
  
   1.  **識別子 (UNB1.1)**、送信インターチェンジに適用する設定の EDIFACT 文字を入力します。 このフィールドは必須です。  
  
   2.  **バージョン (UNB1.2)**、値を選択**1**と**4**します。 このフィールドの入力は省略可能です。  
  
4. **区切り記号**セクションで、次の操作を行います。  
  
   1.  **コンポーネント データ要素区切り記号 (UNA1)**、複合データ要素内の単純データ要素を区切るコンポーネント データ要素区切り記号の値を入力します。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 文字の書式を変更すると、入力した文字が自動的に変更されます。  
  
   2.  **データ要素区切り記号 (UNA2)**、2 つ以上の単純データ要素または複合に属さない単純データ要素から成る複合データ要素を区切るデータ要素区切り記号の値を入力します。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 文字の書式を変更すると、入力した文字が自動的に変更されます。  
  
   3.  **10 進表記 (UNA3)**、送信インターチェンジで使用する小数点表記を選択します。  
  
   4.  **リリース インジケーター (UNA4)**、直後の文字が構文区切り文字、終端記号、またはリリース文字ではなく、元のデータの一部であることを示すリリース インジケーターの値を入力します。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 文字の書式を変更すると、入力した文字が自動的に変更されます。  
  
   5.  **繰り返し区切り記号 (UNA5)** を分離するために使用される繰り返し区切り記号は、トランザクション セット内で繰り返すをセグメントの値を入力します。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 文字の書式を変更すると、入力した文字が自動的に変更されます。  
  
   6.  **セグメント終端記号 (UNA6)**、EDI セグメントの終端を示すセグメント終端記号の値を入力します。  
  
   7.  **UNA6 サフィックス**、か、BizTalk Server でセグメント識別子と共に使用される文字を選択**None**、 **CR** (復帰) **LF**(改行)、または**CR LF** (キャリッジ リターン/ライン フィード)。 サフィックスを指定した場合は、セグメント終端記号データ要素を空白にすることができます。 セグメント終端記号を空白のままにした場合は、サフィックスを指定する必要があります。 セグメント終端記号とサフィックスの組み合わせとして、次の値のいずれかを指定できます。  
  
       -   [ セグメント終端記号]  
  
       -   セグメント終端記号 + 復帰  
  
       -   セグメント終端記号 + 復帰/改行  
  
       -   キャリッジ リターン  
  
       -   ライン フィード  
  
       -   キャリッジ リターン/ライン フィード  
  
5. クリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**を検証し、変更を確定し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理に対する EDIFACT フォールバック アグリーメント プロパティの構成](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)