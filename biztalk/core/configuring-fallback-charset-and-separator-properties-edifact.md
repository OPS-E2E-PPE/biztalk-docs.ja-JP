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
ms.openlocfilehash: 73214ab78dfb262113df25e55cec76b6cc08f473
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355723"
---
# <a name="configuring-fallback-charset-and-separator-properties-edifact"></a>フォールバック文字セットと区切り記号 (EDIFACT) のプロパティを構成します。
フォールバック アグリーメントで、文字のセット (UNA) を指定できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、送信 EDIFACT メッセージのエンベロープを作成するときにパーティのプロパティの検証に使用します。 区切り記号と終端記号 (UNB) は、インターチェンジ内のセグメントの使用が指定することもできます。  
  
 UNA セグメントでは、BizTalk Server が、パーティに送信する EDIFACT エンコード インターチェンジの UNA セグメントを生成する方法を定義します。 UNA セグメントは、EDIFACT エンコード インターチェンジの区切り記号およびインジケータとして使用される文字を定義します。 インターチェンジには、標準以外の区切り文字が含まれている場合にのみ、このセグメントを使用します。  
  
 UNB セグメントでは、使用する設定の EDIFACT 文字を定義します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-character-set-and-separators"></a>文字セットと区切り記号を構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**EDIFACT フォールバックの設定**します。  
  
2. **EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**文字セットと区切り記号**します。  
  
3. **構文 (UNB1)** セクションで、次の操作を行います。  
  
   1.  **識別子 (UNB1.1)**、送信インターチェンジに適用する設定の EDIFACT 文字を入力します。 このフィールドは必須です。  
  
   2.  **バージョン (UNB1.2)**、値を選択**1**と**4**します。 これは、オプションのフィールドです。  
  
4. **区切り記号**セクションで、次の操作を行います。  
  
   1.  **コンポーネント データ要素区切り記号 (UNA1)**、複合データ要素内の単純データ要素を区切るコンポーネント データ要素区切り記号の値を入力します。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 入力した文字は、書式を変更する場合に自動的に変更されます。  
  
   2.  **データ要素区切り記号 (UNA2)**、2 つ以上の単純データ要素または複合に属さない単純データ要素から成る複合データ要素を区切るデータ要素区切り記号の値を入力します。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 入力した文字は、書式を変更する場合に自動的に変更されます。  
  
   3.  **10 進表記 (UNA3)**、送信インターチェンジで使用する小数点表記を選択します。  
  
   4.  **リリース インジケーター (UNA4)**、直後の文字が構文区切り文字、終端記号、またはリリース文字ではなく、元のデータの一部であることを示すリリース インジケーターの値を入力します。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 入力した文字は、書式を変更する場合に自動的に変更されます。  
  
   5.  **繰り返し区切り記号 (UNA5)** を分離するために使用される繰り返し区切り記号は、トランザクション セット内で繰り返すをセグメントの値を入力します。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 入力した文字は、書式を変更する場合に自動的に変更されます。  
  
   6.  **セグメント終端記号 (UNA6)**、EDI セグメントの終端を示すセグメント終端記号の値を入力します。  
  
   7.  **UNA6 サフィックス**、か、BizTalk Server でセグメント識別子と共に使用される文字を選択**None**、 **CR** (復帰) **LF**(改行)、または**CR LF** (キャリッジ リターン/ライン フィード)。 サフィックスを指定する場合、セグメント終端記号データ要素を空にすることができます。 セグメント終端記号を空にする場合は、サフィックスを指定する必要があります。 セグメント終端記号とサフィックスの組み合わせには、次のいずれかを指定できます。  
  
       -   セグメント終端記号  
  
       -   セグメント終端記号 + 復帰  
  
       -   セグメント終端記号 + 復帰とライン フィード  
  
       -   キャリッジ リターン  
  
       -   ライン フィード  
  
       -   キャリッジ リターン/ライン フィード  
  
5. クリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**を検証し、変更を確定し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理に対する EDIFACT フォールバック アグリーメント プロパティの構成](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)