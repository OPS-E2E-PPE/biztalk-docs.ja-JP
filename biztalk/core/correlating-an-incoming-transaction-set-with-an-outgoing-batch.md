---
title: 送信バッチの設定、受信トランザクションの関連付け |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fbe40f8-7379-42be-b8a7-070ce8a7ce26
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d1e0d6b9a26809325d28fd954ae9197ac36ec9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354475"
---
# <a name="correlating-an-incoming-transaction-set-with-an-outgoing-batch"></a>受信トランザクション セットと送信パッチの関連付け
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、バッチ処理オーケストレーションに送信された EDI トランザクション セットを、送信バッチに関連付けることができます。 これを行うには、バッチ処理オーケストレーションに送信されたトランザクション セットの状態レポートのエントリ (BTSInterchangeID) を、オーケストレーションの状態レポートのエントリ (ActivityID) に関連付けます。 この関連付けは、BusinessMessageJournal BAM アクティビティのエントリを使用して行います。 これらのエントリは、バッチ処理オーケストレーションが、バッチ要素の受信時に作成します。  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントで EDI の状態レポートとトランザクション セットの追跡が有効になっている場合にのみ、BusinessMessageJournal アクティビティにエントリが作成されます。  
  
 以下のセクションでは、次の事項について詳しく説明します。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が追跡データを保存する方法  
  
- カスタム パイプライン コンポーネントを作成して関連付けを有効にする方法  
  
- 受信トランザクション セットを送信バッチに関連付ける方法  
  
- バッチに含まれるトランザクション セットの BTSInterchangeID がわかっている場合に、BusinessMessageJournal アクティビティに対してクエリを実行し、バッチの BTSInterchangeID を特定する方法  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
## <a name="changes-to-the-activities"></a>アクティビティに対する変更  
 バッチ処理オーケストレーションは、BatchingActivity、TransactionSetActivity、および BusinessMessageJournal の各 BAM アクティビティにエントリを作成します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を通じてトランザクション セットの処理を行う間に、これらのアクィビティ テーブルに対し、トランザクション セットとそれを含むバッチのエントリを次のように作成します。  
  
1.  EDI 逆アセンブラーは、受信 EDI インターチェンジの処理時に、InterchangeStatusActivity テーブルと TransactionSetActivity テーブルにエントリを作成します。  
  
    > [!NOTE]
    >  BAM アクティビティの詳細については、次を参照してください。 [EDI AS2 メッセージの追跡するために BAM アクティビティ作成](../core/bam-activities-created-to-track-edi-as2-messages.md)です。  
  
2.  バッチ処理オーケストレーションは、インスタンスが作成されたときに、BatchingActivity にエントリを作成します。 BAM サブシステムは、ActivityID の値を作成します。  
  
3.  バッチ処理オーケストレーションは、トランザクション セットの受信時に、TransactionSetActivity テーブルにそのトランザクション セットのエントリを作成します。  
  
4.  オーケストレーションは、BusinessMessageJournal アクティビティにエントリを作成します。 次に、このアクティビティの MessageTrackingID フィールドを、TransactionSetActivity テーブルに作成したエントリの ActivityID フィールドの値に設定します。 さらに、BTSInterchangeID フィールドをトランザクション セットの BTS.InterchangeID コンテキスト プロパティに、BTSMessageID フィールドをトランザクション セットの BTS.MessageID コンテキスト プロパティに設定します。  
  
5.  オーケストレーションは、BusinessMessageJournal アクティビティに 2 つ目のエントリを作成します。 次に、MessageTrackingID フィールドを、TransactionSetActivity テーブルに作成したエントリの ActivityID フィールドに設定します。 さらに、BTSInterchangeID フィールドを、バッチの BTS.InterchangeID コンテキスト プロパティに設定します。 また、BTSMessageID は設定せずに、 ContainerActivityID を BatchingActivity の ActivityID の値に設定します。  
  
## <a name="creating-a-custom-pipeline-component-for-enabling-correlation"></a>カスタム パイプライン コンポーネントの作成による関連付けの準備  
 受信トランザクション セットをそのトランザクションを含む、送信バッチの相関関係を設定する設定、カスタム パイプライン コンポーネントを作成する必要があります。 このパイプライン コンポーネントでの処理は、EDI 逆アセンブラーによる処理の後、EDIReceive パイプラインの BatchMarker コンポーネントで処理を行う前に行います。 このパイプライン コンポーネントでは、BusinessMessageJournal アクティビティにエントリを作成する必要があります。 このエントリでは、BTSInterchangeID フィールドを BTS.InterchangeID コンテキスト プロパティに、BTSMessageID フィールドを BTS.MessageID コンテキスト プロパティに設定します。  
  
## <a name="looking-up-the-interchangeid-for-a-transaction-set-in-a-batch"></a>バッチ内トランザクション セットの InterchangeID の検索  
 受信したインターチェンジと、インターチェンジ内のトランザクション セットを含むバッチを関連付けるには、BatchingActivity テーブルと BusinessMessageJournal アクティビティのエントリを使用して、次に示す作業を行います。  
  
### <a name="to-correlate-an-incoming-transaction-set-with-an-outgoing-batch-that-contains-that-transaction-set"></a>受信トランザクション セットとそのトランザクション セットを含む送信バッチを関連付けるには  
  
1.  BatchingActivity テーブルで、バッチの ActivityID の値を特定します。  
  
2.  その ActivityID の値を、BusinessMessageJournal アクティビティ テーブルの ContainerActivityID フィールドで検索します。  
  
3.  ContainerActivityID で特定したレコード内で、バッチに関連付けられている MessageTrackingID フィールドの値を検索します。  
  
4.  BusinessMessageJournal アクティビティ テーブルでバッチに関連付けられている MessageTrackingID フィールドの値を使用して、BusinessMessageJournal アクティビティ テーブル内で同じ MessageTrackingID フィールドの値を持つ他のレコードを検索します。 ここで見つかったレコードが、バッチ処理オーケストレーションによって記録された、バッチ内のトランザクションに関連付けられたレコードです。  
  
5.  BusinessMessageJournal アクティビティ テーブルのトランザクション セットに関連付けられたレコードで、BTSInterchangeID フィールドの値を検索します。  
  
6.  この BTSInterchangeID の値を使用して、カスタムのパイプライン コンポーネントによって BusinessMessageJournal アクティビティ テーブルに作成された、トランザクション セットのレコードを調べることができます。 また、TransactionSetActivity テーブルでも、トランザクション セットのレコードを検索できます。  
  
## <a name="querying-businessmessagejournal"></a>BusinessMessageJournal に対するクエリの実行  
 トランザクション セットのレポートが有効になっており、受信したインターチェンジの BTSInterchangeID がわかっている場合は、次の SQL クエリを使用して、バッチ処理オーケストレーションに送信されたトランザクション セットを含むバッチの BTSInterchangeID を検索できます。 このコードを使用すると、バッチ内のメッセージを表示するカスタムのアプリケーションを作成できます。  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントで EDI の状態レポートとトランザクション セットの追跡が有効になっている場合にのみ、BusinessMessageJournal アクティビティにエントリが作成されます。  
  
```  
Select MessageTrackingID  
From BusinessMessageJournal  
Where BTSInterchangeID = <given InterchangeID of the receive interchange>  
  
Select BTSInterchangeID  
From BusinessMessageJournal  
Where MessageTrackingID = <MessageTrackingID from the previous query> and BTSInterchangeID = <given InterchangeID>  
```  
  
## <a name="see-also"></a>参照  
 [EDI AS2 メッセージの追跡に作成された BAM アクティビティ](../core/bam-activities-created-to-track-edi-as2-messages.md)   
 [EDI および AS2 状態レポートの有効化](../core/enabling-edi-and-as2-status-reports.md)