---
title: "単一のメッセージにインターチェンジの複数の受信を有効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c98bcd2e-495a-49d8-a471-6e23b1e161f9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec1b282908424100ddfd0363fd6bede9011d53a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-the-receiving-of-multiple-interchanges-in-a-single-message"></a>単一メッセージ内の複数インターチェンジの受信を可能にする
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、複数のインターチェンジを含むメッセージを処理できます。 X12 メッセージには、複数の ISA ヘッダーと IEA トレーラーが含まれています。 EDIFACT メッセージには、複数の UNA/UNB ヘッダーと UNZ トレーラーが含まれています。  
  
 単一メッセージ内の複数のインターチェンジを解析するには、EdiReceive または AS2EdiReceive パイプラインで EDI 逆アセンブラを有効にするには、設定すると、 **DetectMID**パイプライン プロパティを**True**です。 (MID は Mmultiple Interchange Disassembling の略称です)。このプロパティは、既定では True に設定されています。  
  
 EDI 逆アセンブラーを含む受信パイプラインが、複数のインターチェンジを含むメッセージを受信すると、逆アセンブラーが、各インターチェンジをインターチェンジ ヘッダーからインターチェンジ トレーラーまで解析します。 この処理は、次のルールに従って行われます。  
  
-   同じメッセージ内にあるすべてのインターチェンジに対して、同じ種類のエンコード (X12 または EDIFACT) が使用されている必要があります。 メッセージ内のインターチェンジに複数の種類のエンコードが使用されている場合、EDI 逆アセンブラーは、メッセージ内の最初のインターチェンジと同じ種類のエンコードが使用されているすべてのインターチェンジを処理します。 逆アセンブラーは、最初のインターチェンジに使用されているエンコードと異なる種類のエンコードが使用されているインターチェンジはすべて無視します。  
  
-   EDI 逆アセンブラーは、インターチェンジのインターチェンジ トレーラーと、その次のインターチェンジのインターチェンジ ヘッダーの間にある文字をすべて無視します。  
  
-   どちらかを選択して認証を有効にする場合、**認証が失敗した場合は、メッセージをドロップ**または**認証が失敗した場合は、メッセージを保持する**し、受信ポートのプロパティ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]されますメッセージ内の複数のインターチェンジのいずれかが失敗した場合は、メッセージ全体を中断します。  
  
-   認証を有効にした場合、同じメッセージ内にアグリーメントに対して解決されないインターチェンジが 1 つでも存在すると、メッセージ内のすべてのインターチェンジが中断され、アグリーメントに対して解決されたインターチェンジについても受信確認は返されません。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-enable-the-receiving-of-multiple-interchanges-in-a-message"></a>メッセージ内の複数のインターチェンジの受信を可能にするには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**受信場所**ノードを右クリックを複数の受信を有効にする受信場所は、インターチェンジの 1 つのメッセージにし、をクリックして**プロパティ**です。  
  
2.  受信パイプライン (EdiReceive または AS2EdiReceive のいずれか) の横にある省略記号をクリックします。  
  
3.  **パイプラインの構成**ダイアログ ボックスで、設定、 **DetectMID**パイプライン プロパティを**True**です。  
  
4.  をクリックして**[ok]**、をクリックして**OK**もう一度です。  
  
## <a name="see-also"></a>参照  
 [EDI ソリューションのポートを構成します。](../core/configuring-ports-for-an-edi-solution.md)