---
title: パーティの解決パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ad728ff-4d7c-4ab3-af0e-76006576dce5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a466c2de29859b6a971fd34540d6a806da9fe1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977083"
---
# <a name="party-resolution-pipeline-component"></a>パーティの解決パイプライン コンポーネント

## <a name="overview"></a>概要
パーティの解決パイプライン コンポーネントの機能は、送信者の証明書または送信者のセキュリティ ID (SID) を、対応する構成済み BizTalk Server パーティにマップすることです。  

 2 つのメッセージ コンテキスト プロパティを入力として受け取るパーティの解決コンポーネントは、受信メッセージを読み取り、ときに: **WindowsUser**と**SignatureCertificate**します。 **WindowsUser**プロパティは、アダプターによって、または送信者の情報を確実に取得することができる場合、送信者のユーザー名のカスタム パイプライン コンポーネントによって設定されます。 **SignatureCertificate**は、アダプター、またはクライアント認証証明書の拇印を持つ、MIME/SMIME デコーダー パイプライン コンポーネントによって設定されます。  

 メッセージが署名されている場合、受信メッセージの署名の検証で使用された証明書の拇印は、構成リポジトリを検索し、メッセージが関連付けられているパーティを判別するために使用されます。 パーティが見つかった場合、そのパーティの SourcePartyID がメッセージの発信者としてメッセージのコンテキストに配置されます。  

 パーティの解決パイプライン コンポーネントで Windows ユーザーを検証できるようにするには、パーティに "WindowsUser" エイリアスを追加する必要があります。 名前 [修飾子] フィールドに"WindowsUser"を入力し、値の形式でユーザー名を設定\<domain \user name\> (somedomain \someuser など)。 スタンドアロンのシナリオの場合、パーティの構成に使用される WindowsUser 値は、受信アダプターによって設定される値に一致する必要があります。  

 プロパティの両方のパーティの解決コンポーネントで、メッセージが到着した場合、パーティの解決コンポーネントが、証明書によってパーティを解決するのにはまず (と仮定すると、**証明書によるパーティを解決するには**プロパティは、設定**True**)。 パイプラインを実行しているホスト プロセスが付いている場合、パーティが解決された場合は、そのパーティの SourcePartyID がメッセージの OriginatorPID として配置されて、メッセージのコンテキストで**信頼されている認証**パイプラインによって。 証明書を使用してパーティの解決を完了できない場合、メッセージの OriginatorPID 値には、匿名ユーザーの SID である "s-1-5-7" が設定されます。 OriginatorPID プロパティの詳細については、次を参照してください。[パイプラインをセキュリティで保護する方法](../core/how-to-secure-pipelines.md)します。  

## <a name="resolve-the-party"></a>パーティを解決します。  
 次の表に、パーティの解決パイプライン コンポーネントがパーティを解決する方法を示します。  

|SID を使用|証明書を使用|WindowsUser|SignatureCertificate|結果|  
|------------|--------------------|-----------------|--------------------------|------------|  
|True|False|使用可能です|使用可能または使用不可|パーティが解決されます。|  
|True|False|利用不可|使用可能または使用不可|パーティは解決されず、匿名として設定されます。|  
|False|True|使用可能または使用不可|使用可能または使用不可|パーティは解決されず、匿名として設定されます。|  
|True|True|使用可能です|使用可能です|パーティが解決されます。|  
|True|True|利用不可|使用可能または使用不可|パーティは解決されず、匿名として設定されます。|  
|False|False|使用可能または使用不可|使用可能または使用不可|パーティは解決されず、匿名として設定されます。|  

 パーティの解決パイプライン コンポーネントの構成方法の詳細については、次を参照してください。[パーティの解決パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-party-resolution-pipeline-component.md)します。  

## <a name="see-also"></a>参照  
- **メッセージ コンテキスト プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [パイプライン コンポーネント](../core/pipeline-components.md)   
- [カスタム パーティの解決 (BizTalk Server サンプル)](../core/custom-party-resolution-biztalk-server-sample.md)   
- [プロセス間のメッセージの認証](../core/authentication-of-messages-between-processes.md)
