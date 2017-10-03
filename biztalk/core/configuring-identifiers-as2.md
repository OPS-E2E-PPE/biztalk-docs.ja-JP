---
title: "識別子 (AS2) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29f12696-8257-4664-8e61-292678e98b6b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac5f85187a49f3ab5248f12aceba74731ed7e915
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-identifiers-as2"></a>識別子の構成 (AS2)
パートナー アグリーメントで、送信パーティおよび受信パーティを指定する必要があります。 これらの値は、受信メッセージおよび送信メッセージのアグリーメントの解決にも使用されます。  
  
> [!IMPORTANT]
>  オフにした場合、このページで、次のプロパティが無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
>   
>  -   **AS2To** **追加のアグリーメント リゾルバー**セクションです。  
>   
>  プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-identifier-properties"></a>識別子のプロパティを構成するには  
  
1.  AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブで、をクリックして**識別子**です。  
  
3.  **AS2-から** ページで、AS2 メッセージを送信する取引先の名前を指定します。  
  
4.  **AS2-に** ページで、AS2 メッセージを受信する取引先の名前を指定します。  
  
5.  下にある、**追加のアグリーメント リゾルバー**  セクションの**AS2To**プロパティ、メッセージを受信する取引先の追加の別名を入力します。  
  
    > [!NOTE]
    >  このプロパティは省略可能です。 このプロパティは下位互換用に使用されます。 BizTalk Server 2006 R2 または BizTalk Server 2009 から [!INCLUDE[prague](../includes/prague-md.md)] にパーティ定義を移行した場合、以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパーティ名は、このプロパティの値として含められます。 これにより、アグリーメントの解決が実行され、既存のアプリケーションおよび取引先の定義を [!INCLUDE[prague](../includes/prague-md.md)] で使用できるようになります。  
  
6.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [AS2 アグリーメント プロパティの構成](../core/configuring-as2-agreement-properties.md)