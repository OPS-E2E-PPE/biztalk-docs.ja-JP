---
title: エンベロープ (X12 インターチェンジの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4fade73-14cf-475c-81b5-6102c75db991
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b2371943f1c422addf5ac31682f92cf36bd368
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355770"
---
# <a name="configuring-envelopes-x12-interchange-settings"></a>エンベロープの構成 (X12 インターチェンジの設定)
X12 インターチェンジのエンベロープの生成の設定を定義する方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信側パーティに送信する X12 エンコード インターチェンジのエンベロープを生成します。 このセクションで定義する方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パーティに送信する X12 エンコード インターチェンジの ISA セグメントを生成します。 ISA セグメントは、X12 エンコード インターチェンジのインターチェンジ制御ヘッダーです。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム、英数字の ISA フィールドの長さは固定です。 ただし、[!INCLUDE[TPM](../includes/tpm-md.md)]ユーザー インターフェイスでは、英数字の ISA フィールドの 1 つの文字を入力することがあります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] これらのフィールドでは、標準要件に準拠するための末尾の空白文字が埋め込まれます。  
> 
> [!NOTE]
>  ここで説明した設定は、HIPAA インターチェンジのエンベロープの生成にも適用されます。  
> 
> [!IMPORTANT]
>  オフにした場合、このページで、すべてのプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。  
> 
>  プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-define-the-envelope"></a>エンベロープを定義するには  
  
1. X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2. 一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**エンベロープ**します。  
  
3. **ISA11 の使用法**、保持**標準識別子**繰り返し区切り記号ではなく標準識別子を指定し、ドロップダウン リストから標準識別子の値を選択します。 選択**繰り返し区切り記号**を標準の識別子ではなく繰り返し区切り記号を指定し、繰り返し区切り記号として単一の文字を入力します。 トランザクション セット内で繰り返すセグメントを区切るために使用される繰り返し区切り記号は、ASCII 文字セット内の値に制限されます。  
  
4. **制御バージョン番号 (ISA12)**、X12 で使用される標準のバージョンを選択[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信インターチェンジを生成するためです。  
  
5. **使用状況インジケーター (ISA15)** 選択によって、インターチェンジが生成されるかどうかを指定すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]情報、実稼働データ、またはテスト データ。  
  
6. をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジの設定の構成 (X12)](../core/configuring-interchange-settings-x12.md)