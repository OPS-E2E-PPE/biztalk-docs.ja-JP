---
title: フォールバック識別子 (X12) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cb5b32c-96ec-4192-9a10-6668a2cb1195
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cced4cbb22be0f486542f092946462906bd674df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998227"
---
# <a name="configuring-fallback-identifiers-x12"></a>フォールバック識別子の構成 (X12)
未承認の受信者がインターチェンジを受信していないことを確認するには、フォールバック アグリーメントで、X12 認証とセキュリティのプロパティを設定する必要があります。  
  
> [!NOTE]
>  ここで説明するインターチェンジ処理プロパティは、HIPAA インターチェンジにも当てはまります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-set-sender-receiver-and-security-properties"></a>送信者、受信者、セキュリティのプロパティを設定するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。  
  
2. **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[ **識別子**.  
  
3. 値を入力、 **ISA1 2 (認証修飾子およびセキュリティ情報)** します。 値を選択、**認証修飾子 (ISA1)** 関連付けられているドロップダウン リストから。 この値は、以外の場合**00**の**値 (ISA2)** テキスト ボックスに、1 文字の英数字の最小値と最大 10 個を入力します。 このフィールドの入力は省略可能です。 これらの値を指定する場合は、受信したインターチェンジの ISA1 フィールドと ISA2 フィールドが一致するようにしてください。それ以外の場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジを中断します。  
  
4. 値を入力、 **ISA3 ~ 4 (セキュリティ修飾子およびセキュリティ情報)** します。 値を選択、**セキュリティ修飾子 (ISA3)** ドロップダウン リストから。 この値は、以外の場合**00**、用、**値 (ISA4)** テキスト ボックスに、1 つの英数字値の最小値、最大 10 個を入力します。 このフィールドの入力は省略可能です。 これらの値が、受信したインターチェンジの ISA3 フィールドおよび ISA4 フィールドと一致しない場合、インターチェンジは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって中断されます。  
  
   > [!NOTE]
   >  値**03 – パスワード (旧バージョンとの互換性) 用**、旧バージョンと互換性のために含まれる[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]は将来のバージョンで削除されます。  
  
5. 値を入力**ISA5 ~ 6 (送信者の修飾子と識別子)** します。 修飾子の値を選択、**送信者 Id 修飾子 (ISA5)** ドロップダウン リスト。 識別子についての**値 (ISA6)** テキスト ボックスに、1 文字の英数字の最小値と最大 15 文字を入力します。  
  
6. 値を入力 **[isa7] ~ 8 (受信者の修飾子と識別子)** します。 修飾子の値を選択、**受信者 Id 修飾子 (ISA7)** ドロップダウン リスト。 識別子についての**値 (ISA8)** テキスト ボックスに、1 文字の英数字の最小値と最大 15 文字を入力します。  
  
7. をクリックして**適用**を変更を受け入れるか、をクリックする**OK**を入力し、変更を検証して、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)