---
title: フォールバック識別子 (X12) の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 58909783b30a0bce855fc56316f687aa9dbc918c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233530"
---
# <a name="configuring-fallback-identifiers-x12"></a>フォールバック識別子の構成 (X12)
未承認の受信者がインターチェンジを受信していないことを確認するには、フォールバック アグリーメントで、X12 認証とセキュリティのプロパティを設定する必要があります。  
  
> [!NOTE]
>  ここで説明するインターチェンジ処理プロパティは、HIPAA インターチェンジにも当てはまります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-set-sender-receiver-and-security-properties"></a>送信者、受信者、セキュリティのプロパティを設定するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**です。  
  
2.  **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**識別子**.  
  
3.  値を入力して、 **ISA1-2 (認証修飾子および認証情報)** です。 値を選択、**認証修飾子 (ISA1)** 関連付けられているドロップダウン リストからです。 この値は、以外の場合**00**、用、**値 (ISA2)** テキスト ボックスに、1 つの英数字の最小値と最大 10 個を入力します。 このフィールドの入力は省略可能です。 これらの値を指定する場合は、受信したインターチェンジの ISA1 フィールドと ISA2 フィールドが一致するようにしてください。それ以外の場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジを中断します。  
  
4.  値を入力して、 **ISA3 4 (セキュリティ修飾子および認証情報)** です。 値を選択、**セキュリティ修飾子 (ISA3)** ドロップダウン リストからです。 この値は、以外の場合**00**、用、**値 (ISA4)** テキスト ボックスに、1 つの英数字値の最小値と最大 10 個を入力します。 このフィールドの入力は省略可能です。 これらの値が、受信したインターチェンジの ISA3 フィールドおよび ISA4 フィールドと一致しない場合、インターチェンジは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって中断されます。  
  
    > [!NOTE]
    >  値**03 – パスワード (下位互換用**が旧バージョンと互換性のために含まれる[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]し、将来のバージョンで削除される予定です。  
  
5.  値を入力します **(送信者の修飾子と識別子) の ISA5 ~ 6**です。 修飾子の値を選択、**送信者 Id 修飾子 (ISA5)** ドロップダウン リスト。 、識別子ので、**値 (ISA6)** テキスト ボックスに、1 つの英数字の最小値と最大 15 文字を入力します。  
  
6.  値を入力します **[isa7] ~ 8 (受信者の修飾子と識別子)** です。 修飾子の値を選択、**受信者 Id 修飾子 (ISA7)** ドロップダウン リスト。 、識別子ので、**値 (ISA8)** テキスト ボックスに、1 つの英数字の最小値と最大 15 文字を入力します。  
  
7.  をクリックして**適用**を変更を受け入れるか、をクリックして**OK**入力と、変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [設定の X12 インターチェンジ処理のためのフォールバック アグリーメント プロパティ](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)