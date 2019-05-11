---
title: フォールバック エンベロープ プロパティ (X12 インターチェンジの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e9b05ea-2a0f-42d6-adc2-c1f1f2b7a993
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a6e7af661992db4067bd62d53b58322c486ec57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355667"
---
# <a name="configuring-fallback-envelope-properties-x12-interchange-settings"></a>フォールバック エンベロープ プロパティの構成 (X12 インターチェンジの設定)
X12 インターチェンジのエンベロープの生成の設定を定義する方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信側パーティに送信する X12 エンコード インターチェンジのエンベロープを生成します。 このフォールバック アグリーメントで定義する方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パーティに送信する X12 エンコード インターチェンジの ISA セグメントを生成します。 ISA セグメントは、X12 エンコード インターチェンジのインターチェンジ制御ヘッダーです。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム、英数字の ISA フィールドの長さは固定です。 ただし、[!INCLUDE[TPM](../includes/tpm-md.md)]ユーザー インターフェイスでは、英数字の ISA フィールドの 1 つの文字を入力することがあります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] これらのフィールドでは、標準要件に準拠するための末尾の空白文字が埋め込まれます。  
> 
> [!NOTE]
>  ここで説明した設定は、HIPAA インターチェンジのエンベロープの生成にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-define-the-envelope"></a>エンベロープを定義するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。  
  
2. **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**エンベロープ**.  
  
3. **ISA11 の使用法**、保持**標準識別子**繰り返し区切り記号ではなく標準識別子を指定し、ドロップダウン リストから標準識別子の値を選択します。 選択**繰り返し区切り記号**を標準の識別子ではなく繰り返し区切り記号を指定し、繰り返し区切り記号として単一の文字を入力します。 トランザクション セット内で繰り返すセグメントを区切るために使用される繰り返し区切り記号は、ASCII 文字セット内の値に制限されます。  
  
4. **制御バージョン番号 (ISA12)**、X12 で使用される標準のバージョンを選択[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信インターチェンジを生成するためです。  
  
5. **使用状況インジケーター (ISA15)** 選択によって、インターチェンジが生成されるかどうかを指定すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]情報、実稼働データ、またはテスト データ。  
  
6. をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)