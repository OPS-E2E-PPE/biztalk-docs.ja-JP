---
title: 送信ポートの関連付け (EDIFACT) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7faabc7-072c-408c-bbd5-f0a039be81f8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4762af77250eaf17624e643f62e0214953ca4118
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390766"
---
# <a name="configuring-send-port-association-edifact"></a>送信ポートの関連付けの構成 (EDIFACT)
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信 EDI インターチェンジのアグリーメントを解決するのには、ポートの関連付けを送信します。 EDI インターチェンジは、アグリーメントに関連付けられている送信ポートとメッセージをサブスクライブした送信ポートを照合してアグリーメントに解決されます。 このトピックでは、アグリーメントに送信ポートに関連付ける方法の手順を示します。  
  
> [!NOTE]
>  1 つの送信ポートは複数のアグリーメントに関連付け、BizTalk Server はエラーを生成します。  
  
> [!IMPORTANT]
>  BizTalk Server では、送信ポートの関連付けはアグリーメント レベルでのみ行われます。 ただし、BizTalk Server 2009 で送信ポートが関連付けられているパーティ レベルで。 旧バージョンとの互換性のため、**送信ポート**ページも用意されて、パーティのプロパティの一部として (を参照してください[全般的なパーティ プロパティを構成する](../core/configuring-general-party-properties.md))。 送信ポートをアグリーメントと関連付けるたびに、送信ポート設定がパーティ設定にも反映され、このページにも送信ポートの関連付けが表示されます。 ただし、その逆は真ではありません。 送信ポートをパーティと関連付け、その送信ポートをアグリーメント設定の一部として自動的に利用可能にすることはできません。  
  
> [!IMPORTANT]
>  オフにした場合に、このページで、送信ポートの関連付けグリッドが無効になって、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときにアグリーメント。  
>   
>  グリッドは、パーティから送信されるインターチェンジのプロパティに対応する一方向アグリーメント タブでのみ無効になります。 たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A について、グリッドが無効になりますで、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-associate-send-ports-with-an-agreement"></a>送信ポートをアグリーメントに関連付ける  
  
1.  EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**送信ポート**します。  
  
3.  空のセルをクリックして、**名前**列で、ドロップダウン リストから、アグリーメントと関連付ける送信ポートを選択します。 **URI**列には、送信ポートのアドレスが表示されます。  
  
4.  送信ポートの関連付けを削除する送信ポートの行を選択し、をクリックして**削除**します。  
  
5.  送信ポートのプロパティを表示する送信ポートの行を選択し、をクリックして**プロパティ**します。  
  
6.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジの設定の構成 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)