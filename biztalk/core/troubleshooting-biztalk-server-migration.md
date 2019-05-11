---
title: BizTalk Server の移行のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 931dd72f3c6ffc73209fca61a1c75becd30151c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398678"
---
# <a name="troubleshooting-biztalk-server-migration"></a>BizTalk Server の移行のトラブルシューティング
このセクションで、1 か所から BizTalk アプリケーションの移行中に発生した一般的な問題に関する情報を提供します[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を BizTalk Server 2009 です。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="custom-applications-might-not-work-while-upgrading"></a>アップグレード中、カスタム アプリケーションが動作しない可能性がある  
  
##### <a name="problem"></a>問題  
 アップグレードするときに[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009 から BizTalk Server では、一部のカスタム アプリケーションが機能しません。  
  
##### <a name="cause"></a>原因  
 BizTalk のマネージド コード コンポーネントはすべて、CLR 4.0 上で実行されます。 これらのコンポーネントは [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] に対してコンパイルされるので、CLR 4.0 で実行するための構成ファイルが必要になります。  
  
##### <a name="solution"></a>ソリューション  
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