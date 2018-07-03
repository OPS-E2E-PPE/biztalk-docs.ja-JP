---
title: Windows Server 2003 SP1 および SP2 サービス拒否チェックの無効化 |Microsoft Docs
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
ms.openlocfilehash: 688ff81133e60d5be5ef2f9d6826b9b6ca93919c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979267"
---
# <a name="disabling-windows-server-2003-sp1-and-sp2-denial-of-service-checking"></a>Windows Server 2003 SP1 および SP2 サービス拒否チェックの無効化
> [!NOTE]  
>  このトピックでは、Windows Server 2003 にのみ適用できます。  
  
 サービス チェックの Windows Server 2003 Service Pack 1 および Service Pack 2 の拒否を無効にする必要があります。 これは、ため、一部の負荷が高いシナリオで Windows Server 2003 SP1 および SP2 サービス チェックの拒否が起こる可能性があります誤認する有効な TCP/IP 接続として、サービス拒否攻撃です。  
  
> [!IMPORTANT]  
>  実際のサービス拒否攻撃から低下しないようにすることを確認したら、イントラネットのシナリオでのみこの機能を無効にする必要があります。  
  
## <a name="how-denial-of-service-can-affect-tcpip-connections"></a>サービス拒否が TCP/IP 接続に影響を与える  
 Windows Server 2003 SP1 および SP2 は、サーバーへの同時 TCP/IP 接続のキューのサイズを小さくセキュリティ機能を実装します。 この機能は、サービス拒否攻撃の回避に役立ちます。 負荷条件下で Windows Server 2003 SP1 またはそれ以降は、TCP/IP プロトコル可能性がありますを正しく識別しない有効な TCP/IP 接続をサービス拒否攻撃として。 これが発生するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が過負荷。  
  
## <a name="modifying-the-registry-entry"></a>レジストリ エントリを変更します。  
 詳細については、マイクロソフト サポート技術情報記事 899599 を参照してください["BizTalk Server ホスト インスタンスが失敗すると、BizTalk Server ベースのサーバーは、大量のドキュメントを処理するときに、"一般的なネットワーク"エラーがアプリケーション ログに書き込まれます"。](http://go.microsoft.com/fwlink/?LinkId=158860) (<http://go.microsoft.com/fwlink/?LinkId=158860>). 作成するのには、この記事の手順に従って、 **SynAttackProtect**をホストする SQL Server を実行しているコンピューター上のレジストリ エントリ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースおよび実行しているコンピューターで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows Server を実行しています。2003 SP1 またはそれ以降。  
  
## <a name="tuning-registry-settings-that-govern-the-level-of-denial-of-service-attack-protection"></a>拒否の攻撃からサービスの保護のレベルを制御するレジストリ設定のチューニング  
 特定のシナリオでは、サービス拒否攻撃保護の管理がどの程度積極的にサービスの機能の拒否が適用されるを削減することがあります。 次の手順に従って保護機能をサービス拒否型の既定の動作を調整することができます。  
  
1.  いることを確認、 **SynAttackProtect**レジストリ エントリの REG_DWORD 値に設定されます**1** 」の説明に従って[ http://go.microsoft.com/fwlink/?LinkId=111477](http://go.microsoft.com/fwlink/?LinkId=111477)します。  
  
2.  構成、 **TcpMaxHalfOpen**レジストリ エントリで説明されている[ http://go.microsoft.com/fwlink/?LinkId=111478](http://go.microsoft.com/fwlink/?LinkId=111478)します。  
  
3.  構成、 **TcpMaxHalfOpenRetried**レジストリ エントリで説明されている[ http://go.microsoft.com/fwlink/?LinkId=111479](http://go.microsoft.com/fwlink/?LinkId=111479)します。  
  
## <a name="see-also"></a>参照  
 [運用準備チェックリスト](../technical-guides/operational-readiness-checklists.md)