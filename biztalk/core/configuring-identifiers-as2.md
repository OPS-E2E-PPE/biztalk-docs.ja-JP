---
title: 識別子の構成 (AS2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29f12696-8257-4664-8e61-292678e98b6b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f4ec3f66a2cdbacf99650620551b7762bcd56df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978363"
---
# <a name="configuring-identifiers-as2"></a>識別子の構成 (AS2)
パートナー アグリーメントで、送信パーティおよび受信パーティを指定する必要があります。 これらの値は、受信メッセージおよび送信メッセージのアグリーメントの解決にも使用されます。  
  
> [!IMPORTANT]
>  オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。  
> 
> - **AS2To** **追加のアグリーメント リゾルバー**セクション。  
> 
>   プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-identifier-properties"></a>識別子のプロパティを構成するには  
  
1. AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2. 一方向アグリーメント タブで、次のようにクリックします。**識別子**します。  
  
3. **AS2-から**ページで、AS2 メッセージを送信する取引先パートナーの名前を指定します。  
  
4. **AS2-に**ページで、AS2 メッセージを受信する取引先パートナーの名前を指定します。  
  
5. 下、**追加のアグリーメント リゾルバー**セクションの**AS2To**プロパティ、メッセージを受信するパートナーの追加の別名を入力します。  
  
   > [!NOTE]
   >  このプロパティは省略可能です。 このプロパティは下位互換用に使用されます。 BizTalk Server の以前のバージョンでパーティの名前まで BizTalk Server 2006 R2 または BizTalk Server 2009 からパーティ定義が移行したときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はこのプロパティの値として含まれます。 これにより、アグリーメントの解決の動作を BizTalk サーバーでは、既存のアプリケーションと取引先の定義を使用することができます。  
  
6. をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [AS2 アグリーメントのプロパティの構成](../core/configuring-as2-agreement-properties.md)