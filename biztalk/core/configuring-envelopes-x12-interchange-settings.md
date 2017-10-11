---
title: "エンベロープ (X12 インターチェンジの設定) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4fade73-14cf-475c-81b5-6102c75db991
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4f88ee1e5d786367c1a4bc0f5b2404fd5c1a37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-x12-interchange-settings"></a>エンベロープの構成 (X12 インターチェンジの設定)
X12 インターチェンジのエンベロープの生成の設定は、受信側パーティに送信する X12 エンコード インターチェンジのエンベロープを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でどのように生成するかを定義します。 ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がパーティに送信する X12 エンコード インターチェンジの ISA セグメントをどのように生成するかを定義します。 ISA セグメントは、X12 エンコード インターチェンジのインターチェンジ制御ヘッダーです。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムでは、英数字の ISA フィールドの長さは固定されています。 ただしの場合は、[!INCLUDE[TPM](../includes/tpm-md.md)]ユーザー インターフェイスでは、英数字の ISA フィールドの 1 つの文字を入力することがあります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]標準要件に準拠するための末尾の空白文字でこれらのフィールドが整数です。  
  
> [!NOTE]
>  ここで説明する設定は、HIPAA インターチェンジ エンベロープの生成にも適用されます。  
  
> [!IMPORTANT]
>  オフにした場合のこのページですべてのプロパティは無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
>   
>  プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-define-the-envelope"></a>エンベロープを定義するには  
  
1.  X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**エンベロープ**です。  
  
3.  **ISA11 の使用法**、保持**標準識別子**繰り返し区切り記号の代わりに標準識別子を指定し、ドロップダウン リストから標準識別子の値を選択することを選択します。 選択**繰り返し区切り記号**を標準の識別子ではなく繰り返し区切り記号を指定し、繰り返し区切り記号として単一の文字を入力します。 繰り返し区切り記号は、トランザクション セット内で繰り返すセグメントを区切るために使用されるもので、ASCII 文字セット内の値のみを使用できます。  
  
4.  **制御バージョン番号 (ISA12)**、X12 で使用される標準のバージョンを選択して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信インターチェンジを生成するためです。  
  
5.  **使用状況インジケーター (ISA15)**、インターチェンジがによって生成されたかどうかを示すために [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]情報、実稼働データ、またはテスト データです。  
  
6.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [(X12) インターチェンジの設定を構成します。](../core/configuring-interchange-settings-x12.md)