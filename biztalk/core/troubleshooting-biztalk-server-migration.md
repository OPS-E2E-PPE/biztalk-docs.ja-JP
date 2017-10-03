---
title: "BizTalk Server の移行のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6eddc0a-2403-4bcd-9327-23f51ce7d57b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcdb53c7123b4ffaa2294db080e1efc4fb4eb65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-server-migration"></a>BizTalk Server の移行のトラブルシューティング
このセクションでは、[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] または [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 から [!INCLUDE[prague](../includes/prague-md.md)] に BizTalk アプリケーションを移行するときに発生する一般的な問題に関する情報をまとめて提供します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="custom-applications-might-not-work-while-upgrading"></a>アップグレード中、カスタム アプリケーションが動作しない可能性がある  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] または [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 から [!INCLUDE[prague](../includes/prague-md.md)] へのアップグレード時、一部のカスタム アプリケーションが動作しない可能性があります。  
  
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