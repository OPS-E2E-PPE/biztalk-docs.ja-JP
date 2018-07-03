---
title: フォールバック文字セットと区切り記号のプロパティ (X12) 構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477f4952-6a4e-4e98-a37f-f6e1fe7db3d3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019fdb4262d778ec8f6605b8f3daef1df7881232
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994539"
---
# <a name="configuring-fallback-charset-and-separator-properties-x12"></a>フォールバックの文字セットと区切り記号のプロパティを構成する (X12)
フォールバック アグリーメントでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、送信 X12 メッセージのエンベロープを作成するときにパーティのプロパティを検証するために使用する文字セットを指定できます。 また、インターチェンジのセグメントに使用する区切り記号と終端記号を指定することもできます。  
  
> [!NOTE]
>  ここで説明する設定は、HIPAA インターチェンジにも当てはまります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-character-set-and-separators"></a>文字セットと区切り記号を構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。  
  
2. **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**文字セットと区切り記号**.  
  
3. **使用する文字セット**ドロップダウン リストでは、設定、アグリーメント用に入力したプロパティの検証に使用する文字を X12 を選択します。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、この設定は関連するアグリーメントのプロパティに入力した値の検証にのみ使用されます。 受信パイプラインまたは送信パイプラインでのランタイム処理の実行時には、この文字セット プロパティが無視されます。  
  
4. **データ要素**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つまたは複数の単純データ要素、および複合要素に属さない単純データ要素から成る複合データ要素を区切るには使用されます。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。  
  
5. **コンポーネント要素区切り記号 (ISA16)**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複合データ要素内の単純データ要素を区切るには使用されます。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。  
  
6. **セグメント終端記号**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI セグメントの終端を示すために使用されます。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。  
  
7. **サフィックス**、文字を選択する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]か、セグメント識別子と共に使用**None**、 **CR** (復帰) **LF**(改行)、または**CR LF** (キャリッジ リターン/ライン フィード)。 サフィックスを指定した場合は、セグメント終端記号データ要素を空白にすることができます。 セグメント終端記号を空白のままにした場合は、サフィックスを指定する必要があります。 セグメント終端記号とサフィックスの組み合わせとして、次の値のいずれかを指定できます。  
  
   -   [ セグメント終端記号]  
  
   -   セグメント終端記号 + 復帰  
  
   -   セグメント終端記号 + 復帰/改行  
  
   -   キャリッジ リターン  
  
   -   ライン フィード  
  
   -   キャリッジ リターン/ライン フィード  
  
8. ペイロード データにも、データ、セグメント、またはコンポーネント区切り記号として使用される文字が含まれている場合は、確認**を使用してペイロードの区切り記号を置き換えます**置換文字を指定するとします。 送信 X12 メッセージの生成時に、ペイロード データの区切り記号のインスタンスはすべて指定された文字で置き換えられます。 選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。 形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。  
  
9. をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)