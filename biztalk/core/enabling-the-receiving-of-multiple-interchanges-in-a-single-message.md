---
title: インターチェンジの 1 つのメッセージで複数の受信を有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98bcd2e-495a-49d8-a471-6e23b1e161f9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b27e4fa04957afd2a5bb25d3aa5b73c1c9c2df8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389109"
---
# <a name="enabling-the-receiving-of-multiple-interchanges-in-a-single-message"></a>単一メッセージ内の複数インターチェンジの受信を可能にする
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 複数のインターチェンジを含むメッセージを処理できます。 X12 メッセージを複数の ISA ヘッダーと IEA トレーラーようなメッセージが含まれます。 EDIFACT メッセージの場合、このようなメッセージに複数の UNA/UNB ヘッダーと UNZ トレーラーが含まれます。  
  
 設定する必要があります、単一メッセージ内の複数のインターチェンジを解析するには、EdiReceive または AS2EdiReceive パイプラインで EDI 逆アセンブラを有効にする、 **DetectMID**パイプライン プロパティを**True**します。 (MID は複数インターチェンジの逆アセンブル用)このプロパティは、既定で True に設定されます。  
  
 EDI 逆アセンブラーを含む受信パイプラインは、複数のインターチェンジにメッセージを受信したときに、逆アセンブラーはインターチェンジ ヘッダーからインターチェンジ トレーラーの各インターチェンジを解析します。 この処理は、次の規則に従って行われます。  
  
- 同じエンコードする必要があります、同じメッセージ内のすべてのインターチェンジ X12 または EDIFACT のいずれかを入力します。 メッセージにエンコードの種類を 1 つ以上のインターチェンジが含まれている場合、EDI 逆アセンブラーは、メッセージに最初のインターチェンジと同じエンコードの種類があるすべてのインターチェンジを処理します。 逆アセンブラーでは、最初のインターチェンジからさまざまなエンコードの種類のすべてのインターチェンジを無視します。  
  
- EDI 逆アセンブラーでは、1 つのインターチェンジのインターチェンジ トレーラーと、次のインターチェンジのインターチェンジ ヘッダーの間の任意の文字を無視します。  
  
- いずれかを選択して認証を有効にした場合、**認証が失敗した場合は、メッセージを削除**または**認証が失敗した場合は、メッセージを保持する**し、受信ポートのプロパティ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]されますメッセージ内の複数のインターチェンジのいずれかが失敗した場合は、メッセージ全体を中断します。  
  
- 認証を有効にした場合と同じメッセージのインターチェンジが 1 つが、アグリーメントに解決しない場合は、メッセージ内のすべてのインターチェンジは中断されますし、受信確認は返されません、アグリーメントに対して解決されたインターチェンジについても.  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-enable-the-receiving-of-multiple-interchanges-in-a-message"></a>メッセージ内の複数のインターチェンジの受信を有効にするには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**受信場所**ノードで、複数の受信を可能にする受信場所がインターチェンジの 1 つのメッセージで、クリックして右クリック**プロパティ**します。  
  
2. 受信パイプライン (EdiReceive または AS2EdiReceive のいずれかである必要があります) を横にある省略記号をクリックします。  
  
3. **パイプラインの構成**ダイアログ ボックスで、セット、 **DetectMID**パイプライン プロパティを**True**します。  
  
4. をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
## <a name="see-also"></a>参照  
 [EDI ソリューションのポートの構成](../core/configuring-ports-for-an-edi-solution.md)