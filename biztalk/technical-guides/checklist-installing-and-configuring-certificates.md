---
title: チェックリスト:インストールして、証明書の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76a8f8f6-8d79-4caf-8fba-8cbcb251d461
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c7851d0b688d21bfc8bda28afa78149a1c3904f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295309"
---
# <a name="checklist-installing-and-configuring-certificates"></a>チェックリスト:インストールして、証明書の構成
このトピックでは、BizTalk Server で使用するための証明書を設定するための手順について説明します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|証明書の要件を評価し、証明書に関して、相互の責任について、取引先パートナーと合意にします。|「評価し、証明書の使用を計画」セクション[証明書の管理のベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|秘密キーを使用する場合は、証明機関 (CA) からデジタル署名用の/秘密キー ペアを要求し、取引先に公開キーを送信します。<br /><br /> 公開キーを使用する場合は、取引先パートナー要求、CA からのデジタル署名用の/秘密キー ペアを持ち、公開キーを送信します。|[BizTalk Server 用の証明書のインストール方法](~/technical-guides/how-to-install-certificates-for-biztalk-server.md)|  
|プライベートまたはパブリック キーを適切な証明書ストアにインストールして、取引先が同じ操作を行います。|-   [BizTalk Server の証明書をインストールする方法](~/technical-guides/how-to-install-certificates-for-biztalk-server.md)<br />-のセクションの「証明書をインストールする」[証明書の管理のベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|MIME/SMIME メッセージを証明書を使用している場合は、証明書を使用する BizTalk Server を構成します。|-   [MIME またはメッセージの SMIME 証明書の構成](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)<br />-「MIME/SMIME の証明書を使用する BizTalk Server を構成する」のセクションで[証明書の管理のベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|(省略可能)アダプターを使用した証明書を使用する場合は、証明書を使用するアダプターを構成します。|-   [アダプターで証明書の構成](~/technical-guides/configuring-certificates-with-adapters.md)<br />-「証明書を使用する BizTalk アダプターを構成する」のセクションの[証明書の管理のベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|(省略可能)証明書を使用して、パーティの解決を実行する、する場合は、証明書を使用するパーティを構成します。|[パーティの解決での証明書の構成方法](~/technical-guides/how-to-configure-certificates-for-party-resolution.md)|  
|(省略可能)1 つの BizTalk グループから別の証明書をエクスポート、証明書を BizTalk アプリケーション; 追加します。アプリケーションを .msi ファイルをエクスポートして別の BizTalk グループにアプリケーションをインポートします。|-   [パーティの解決用の証明書を構成する方法](~/technical-guides/how-to-configure-certificates-for-party-resolution.md)<br />-   [アプリケーションを .msi ファイルにエクスポートする方法](~/technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [アプリケーションを .msi ファイルからインポートする方法](~/technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-"をエクスポートする証明書から 1 つ BizTalk グループを別のセクションの[証明書の管理のベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)|  
  
## <a name="see-also"></a>参照  
 [証明書を管理するためのベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)   
 [BizTalk Server の証明書に関する既知の問題](~/technical-guides/known-issues-with-certificates-in-biztalk-server.md)