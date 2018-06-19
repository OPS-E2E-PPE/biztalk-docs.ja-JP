---
title: 受信者の MDN 設定の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae6431d-a2b9-4889-a29c-720e801a644e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dafe17a0ad357b840b31d8a10c67e1ae3cc1e415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233378"
---
# <a name="configuring-receiver-mdn-settings"></a><span data-ttu-id="f7a85-102">受信者の MDN 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f7a85-102">Configuring Receiver MDN Settings</span></span>
<span data-ttu-id="f7a85-103">受信側の MDN 設定の一部として、AS2 メッセージ ヘッダーに基づく MDN 生成を管理するプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7a85-103">As part of receiver MDN settings, you can specify the properties that govern MDN generation based on the AS2 message header.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7a85-104">プロパティが無効**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する** チェック ボックスパーティ A の同じ ページで、ただし、すべてのプロパティが無効にします**パーティ B には、パーティ A が->**   タブの A の作成中に、チェック ボックスを選択した場合</span><span class="sxs-lookup"><span data-stu-id="f7a85-104">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f7a85-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="f7a85-105">Prerequisites</span></span>  
 <span data-ttu-id="f7a85-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7a85-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-receiver-mdn-settings"></a><span data-ttu-id="f7a85-107">受信側の MDN 設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="f7a85-107">To configure receiver MDN settings</span></span>  
  
1.  <span data-ttu-id="f7a85-108">AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="f7a85-108">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="f7a85-109">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="f7a85-109">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f7a85-110">一方向アグリーメント タブの下にある**ローカル ホストの設定**セクションで、**受信者の MDN 設定**です。</span><span class="sxs-lookup"><span data-stu-id="f7a85-110">On a one-way agreement tab, under **Local Host Settings** section, click **Receiver MDN Settings**.</span></span>  
  
3.  <span data-ttu-id="f7a85-111">オンにしなかった場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティに、**検証** ページで、することもできます、MDN を送信しているパーティがある場合、MDN の署名MDN の生成が有効になって、**廃棄で通知を**AS2 ヘッダーが、**廃棄通知オプション**ヘッダーがない署名を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7a85-111">If you did not check the **Use agreement settings for validation and MDN instead of message header** property in the **Validations** page, you can choose to have the party sending the MDN, sign the MDN if generation of the MDN is enabled by the **Disposition-Notification-to** AS2 header, but the **Disposition-Notification-Options** header does not enable signing.</span></span> <span data-ttu-id="f7a85-112">これは、場合に発生**廃棄通知オプション**設定されていないか、または省略可能に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f7a85-112">This can occur if **Disposition-Notification-Options** is either not set or is set to optional.</span></span> <span data-ttu-id="f7a85-113">これを行う をクリックして**廃棄通知オプションのヘッダーがあらかじめ設定されていない場合、または署名 Receipt Protocol ヘッダーが設定されている場合に省略可能な要求された MDN に署名**です。</span><span class="sxs-lookup"><span data-stu-id="f7a85-113">You can do so by clicking **Sign requested MDN if Disposition-Notification-Option header is not preset or if Signed-Receipt-Protocol header is set to optional**.</span></span>  
  
4.  <span data-ttu-id="f7a85-114">内のテキストを入力することができます、 **MDN テキスト**フィールドに、MDN メッセージ (Content-description フィールド) の下に追加、MDN を送信しているパーティです。</span><span class="sxs-lookup"><span data-stu-id="f7a85-114">You can enter a text in the **MDN Text** field to have the party sending the MDN add it to the MDN message (under the Content-Description field).</span></span> <span data-ttu-id="f7a85-115">この設定は、MDN が AS2 ヘッダーまたはアグリーメント プロパティのどちらに基づいて生成されたのかに関係なく、適用できます。</span><span class="sxs-lookup"><span data-stu-id="f7a85-115">This setting is applicable irrespective of whether the MDN was generated based upon the AS2 headers or the agreement properties.</span></span>  
  
5.  <span data-ttu-id="f7a85-116">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f7a85-116">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a85-117">参照</span><span class="sxs-lookup"><span data-stu-id="f7a85-117">See Also</span></span>  
 [<span data-ttu-id="f7a85-118">ローカル ホスト設定の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="f7a85-118">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)