---
title: BizTalk Server の移行のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6eddc0a-2403-4bcd-9327-23f51ce7d57b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ddb6d9780a86183de5a09791de44adda5d57dab
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006059"
---
# <a name="troubleshooting-biztalk-server-migration"></a>BizTalk Server の移行のトラブルシューティング
このセクションでは、1 か所から BizTalk アプリケーションの移行中に発生する一般的な問題に関する情報の[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を BizTalk Server 2009 です。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="custom-applications-might-not-work-while-upgrading"></a>アップグレード中、カスタム アプリケーションが動作しない可能性がある  
  
##### <a name="problem"></a>問題  
 アップグレードするときに[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を BizTalk Server 2009 一部のカスタム アプリケーションは動作しません。  
  
##### <a name="cause"></a>原因  
 BizTalk のマネージ コード コンポーネントはすべて、CLR 4.0 上で実行されます。 これらのコンポーネントは [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] に対してコンパイルされるので、CLR 4.0 で実行するための構成ファイルが必要になります。  
  
##### <a name="solution"></a>解決方法  
 この問題を解決するには、構成ファイルを更新します。  
  
```  
<configuration>  
<startup useLegacyV2RuntimeActivationPolicy="true">  
<supportedRuntime version="v4.0" />  
</startup>  
</configuration>  
```  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング](../core/troubleshooting.md)