---
title: 'チェックリスト: インストールと証明書の構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 5e675a60967b5ee34c40f1711f256aff76362d2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300498"
---
# <a name="checklist-installing-and-configuring-certificates"></a>チェックリスト: インストールと証明書の構成
このトピックでは、BizTalk Server で使用する証明書のセットアップに必要な手順について説明します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|証明書の要件を評価し、相互の証明書に関して責任について取引先と合意にします。|「評価し、証明書の使用を計画」のセクション[証明書の管理のベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|秘密キーを使用する場合は、証明機関 (CA) からデジタル署名用と非公開のキー ペアを要求し、公開キーを取引先に送信します。<br /><br /> 公開キーを使用する場合は、取引パートナー要求、CA からのデジタル署名用と非公開のキー ペアを持ち、公開キーを送信します。|[BizTalk Server の証明書をインストールする方法](~/technical-guides/how-to-install-certificates-for-biztalk-server.md)|  
|適切な証明書ストアに、プライベートまたはパブリック キーをインストールし、取引パートナーに、同じ操作を実行します。|-   [BizTalk Server の証明書をインストールする方法](~/technical-guides/how-to-install-certificates-for-biztalk-server.md)<br />"証明書の「インストール[証明書管理のベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|証明書を使用して、MIME/SMIME メッセージの証明書を使用する BizTalk Server を構成します。|-   [MIME または SMIME メッセージの証明書の構成](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)<br />-「MIME/SMIME の証明書を使用する BizTalk Server を構成する」のセクションで[証明書の管理のベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|(省略可能)でアダプターを、証明書を使用している場合は、証明書を使用するアダプターを構成します。|-   [アダプターで証明書の構成](~/technical-guides/configuring-certificates-with-adapters.md)<br />「証明書を使用する BizTalk アダプターを構成する」セクション[証明書の管理のベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|(省略可能)証明書を使用して、パーティの解決を実行する、証明書を使用するパーティを構成します。|[パーティの解決用の証明書を構成する方法](~/technical-guides/how-to-configure-certificates-for-party-resolution.md)|  
|(省略可能)別に 1 つの BizTalk グループから証明書をエクスポートする場合、証明書、BizTalk アプリケーションに追加します。.msi ファイルにアプリケーションをエクスポートします。別の BizTalk グループにアプリケーションをインポートします。|-   [パーティの解決用の証明書を構成する方法](~/technical-guides/how-to-configure-certificates-for-party-resolution.md)<br />-   [アプリケーションを .msi ファイルにエクスポートする方法](~/technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [アプリケーションを .msi ファイルからインポートする方法](~/technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-」をエクスポートする証明書から 1 つ「BizTalk グループを別セクションの[証明書管理のベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)|  
  
## <a name="see-also"></a>参照  
 [証明書を管理するためのベスト プラクティス](~/technical-guides/best-practices-for-managing-certificates2.md)   
 [BizTalk Server での証明書に関する既知の問題](~/technical-guides/known-issues-with-certificates-in-biztalk-server.md)