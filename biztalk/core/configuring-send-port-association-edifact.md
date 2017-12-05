---
title: "送信ポートの関連付け (EDIFACT) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7faabc7-072c-408c-bbd5-f0a039be81f8
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 629bde13f8edc9074b3e6bcb4741746e3de8e1a6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-send-port-association-edifact"></a>送信ポートの関連付けの構成 (EDIFACT)
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では送信ポートの関連付けを使用して、送信 EDI インターチェンジのアグリーメントを解決します。 メッセージにサブスクライブする送信ポートをアグリーメントと関連付けられた送信ポートと一致させることで、EDI インターチェンジはアグリーメントに解決されます。 このトピックでは、送信ポートをアグリーメントと関連付ける方法について説明します。  
  
> [!NOTE]
>  1 つの送信ポートが複数のアグリーメントに関連付けられていると、BizTalk Server によってエラーが生成されます。  
  
> [!IMPORTANT]
>  BizTalk Server では、送信ポートの関連付けはアグリーメント レベルでのみ行われます。 ただし、BizTalk Server 2009 で送信ポートはパーティ レベルで関連付けられました。 旧バージョンとの互換性のため、**送信ポート**ページも用意されて、パーティのプロパティの一部として (を参照してください[全般的なパーティ プロパティを構成する](../core/configuring-general-party-properties.md))。 送信ポートをアグリーメントと関連付けるたびに、送信ポート設定がパーティ設定にも反映され、このページにも送信ポートの関連付けが表示されます。 ただし、その逆は真ではありません。 送信ポートをパーティと関連付け、その送信ポートをアグリーメント設定の一部として自動的に利用可能にすることはできません。  
  
> [!IMPORTANT]
>  オフにした場合に、このページで、送信ポートの関連付けグリッドが無効になって、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成中にはアグリーメント。  
>   
>  グリッドは、パーティから送信されるインターチェンジのプロパティに対応する一方向のアグリーメント タブでのみ無効になります。 たとえば、2 つのパーティのパーティ A とパーティ B を作成して、パーティ A に対しては、チェック ボックスをオフ、グリッドが無効な場合、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-associate-send-ports-with-an-agreement"></a>送信ポートをアグリーメントと関連付けるには  
  
1.  EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**送信ポート**です。  
  
3.  下の空のセルをクリックして、**名前**列で、ドロップダウン リストからアグリーメントと関連付ける送信ポートを選択します。 **URI**列には、送信ポートのアドレスが表示されます。  
  
4.  送信ポートの関連付けを削除する送信ポートの行を選択し、をクリックして**削除**です。  
  
5.  送信ポートのプロパティを表示する送信ポートの行を選択し、をクリックして**プロパティ**です。  
  
6.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジの設定の構成 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)