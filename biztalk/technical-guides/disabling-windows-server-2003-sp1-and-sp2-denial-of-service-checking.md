---
title: Windows Server 2003 SP1 および SP2 サービス拒否の状態チェックを無効化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8822c1e4-d146-4361-b25a-7b81cd5cdd3b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b33333efd055a659557513ecc8e0b53a42bc30ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297714"
---
# <a name="disabling-windows-server-2003-sp1-and-sp2-denial-of-service-checking"></a>Windows Server 2003 SP1 および SP2 サービス拒否の状態チェックを無効にします。
> [!NOTE]  
>  このトピックでは、Windows Server 2003 にのみ適用します。  
  
 サービス チェックの Service Pack 2 および Windows Server 2003 Service Pack 1 の拒否を無効にする必要があります。 高負荷状況によっては、サービスのチェックの Windows Server 2003 SP1 および SP2 拒否が起こる可能性がありますを誤って指定 TCP/IP 接続が有効、サービス拒否攻撃としてためにです。  
  
> [!IMPORTANT]  
>  実際のサービス拒否攻撃から低下しないようにすることを確認したら、イントラネットの場合にのみ、この機能を無効にする必要があります。  
  
## <a name="how-denial-of-service-can-affect-tcpip-connections"></a>サービス拒否攻撃が TCP/IP 接続に与える影響について  
 Windows Server 2003 SP1 および SP2 は、サーバーへの同時 TCP/IP 接続のキューのサイズを小さくセキュリティ機能を実装します。 この機能は、サービス拒否攻撃の回避に役立ちます。 負荷が高い状況で、TCP/IP プロトコルを Windows Server 2003 SP1 またはそれ以降の場合がありますを正しく識別されません TCP/IP 接続が有効、サービス拒否攻撃として。 これが発生するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が過負荷します。  
  
## <a name="modifying-the-registry-entry"></a>レジストリ エントリを変更します。  
 詳細については、Microsoft サポート技術情報の記事 899599 を参照してください["BizTalk Server ホスト インスタンスが失敗し、BizTalk Server ベースのサーバーが大量のドキュメントを処理するときに一般的なネットワーク エラーがアプリケーション ログに書き込まれます"。](http://go.microsoft.com/fwlink/?LinkId=158860) (http://go.microsoft.com/fwlink/?LinkId=158860)。 作成するのには、この記事の手順に従って、 **SynAttackProtect**をホストする SQL Server を実行しているコンピューター上のレジストリ エントリ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースおよび実行しているコンピューターで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows Server で実行されています。2003 SP1 またはそれ以降。  
  
## <a name="tuning-registry-settings-that-govern-the-level-of-denial-of-service-attack-protection"></a>サービス拒否攻撃攻撃保護のレベルを制御するレジストリ設定のチューニング  
 特定のシナリオでは、サービス拒否攻撃保護の管理が、サービスの機能の拒否攻撃が適用されるどの程度積極的に削減できます。 次の手順に従って保護機能のサービスの拒否の既定の動作を調整できます。  
  
1.  いることを確認、 **SynAttackProtect**レジストリ エントリがの REG_DWORD 値に設定されている**1** 」の説明に従って[http://go.microsoft.com/fwlink/?LinkId=111477](http://go.microsoft.com/fwlink/?LinkId=111477)です。  
  
2.  構成、 **TcpMaxHalfOpen**レジストリ エントリの説明に従って[http://go.microsoft.com/fwlink/?LinkId=111478](http://go.microsoft.com/fwlink/?LinkId=111478)です。  
  
3.  構成、 **TcpMaxHalfOpenRetried**レジストリ エントリの説明に従って[http://go.microsoft.com/fwlink/?LinkId=111479](http://go.microsoft.com/fwlink/?LinkId=111479)です。  
  
## <a name="see-also"></a>参照  
 [運用の準備のチェックリスト](../technical-guides/operational-readiness-checklists.md)